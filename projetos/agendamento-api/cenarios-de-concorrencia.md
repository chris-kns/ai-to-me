# Cenário: dois clientes, o mesmo horário

> "Dois clientes tentam agendar o mesmo horário ao mesmo tempo. O que acontece? Quem passa na frente?" É o tipo de problema que tutoriais não mostram e que entrevistas adoram.

## O que dá errado (check-then-act)

```text
Cliente A                          Cliente B
1. horário livre? -> sim
                                   2. horário livre? -> sim
3. INSERT agendamento (A)
                                   4. INSERT agendamento (B)   <- double booking
```

A validação existe em **ambos** os fluxos. O que falha é a janela entre "checar" e "gravar". Nenhum `if` no código da aplicação fecha essa janela sozinho.

## Experimento (Semana 8, sábado)

1. Escreva um script que dispare 2 (depois 20) requisições simultâneas para o mesmo horário (`asyncio.gather` com `httpx`, ou threads).
2. **Prove o problema:** mostre no banco duas linhas conflitantes.
3. Aplique uma estratégia da tabela abaixo.
4. **Prove a correção:** repita o experimento e mostre que só uma passa e a outra recebe um erro claro.
5. Registre a decisão em um ADR ([modelo](adr/0000-template.md)).

## Estratégias para comparar

| Estratégia | Como funciona | Pontos de atenção |
|------------|---------------|-------------------|
| **Constraint de exclusão** (PostgreSQL) | O banco rejeita linhas cujo intervalo de tempo se sobrepõe para o mesmo profissional | Garantia forte e declarativa. Exige `btree_gist`. Específica do PostgreSQL |
| **Lock pessimista** (`SELECT ... FOR UPDATE`) | Trava linhas dentro da transação enquanto você checa e grava | Trava só linhas que **existem**: um `INSERT` novo passa. Trave uma linha "mestre" (o profissional) como mutex |
| **Isolamento `SERIALIZABLE`** | O banco detecta o conflito e aborta uma das transações | Exige **retry** na aplicação. Custo de desempenho |
| **Slots discretos + `UNIQUE`** | Horários pré-gerados (profissional + início) com unicidade | Simples e robusto, mas rígido: durações variáveis complicam |
| **Advisory lock** (`pg_advisory_xact_lock`) | Mutex lógico por profissional, liberado no fim da transação | Funciona, mas a regra fica fora do schema |
| **Chave de idempotência** | O cliente envia uma chave por tentativa; repetir não cria outro | Resolve o duplo clique, **não** resolve dois clientes diferentes |

## Perguntas para o ADR

- Qual estratégia escolhi e por quê?
- O que a API devolve ao perdedor da corrida (`409 Conflict`?) e como o cliente deve reagir?
- O que acontece se a transação falhar no meio?
- Como eu **testo** isso de forma repetível?
- O que muda se o sistema passar a ter várias instâncias da API?

<details>
<summary>Referência rápida (só abra depois de tentar sozinho)</summary>

Exemplo de constraint de exclusão no PostgreSQL:

```sql
CREATE EXTENSION IF NOT EXISTS btree_gist;

ALTER TABLE agendamentos
  ADD CONSTRAINT sem_sobreposicao
  EXCLUDE USING gist (
    profissional_id WITH =,
    tstzrange(inicio, fim) WITH &&
  ) WHERE (status = 'confirmado');
```

Leitura: [Range types](https://www.postgresql.org/docs/current/rangetypes.html), [Explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html), [Transaction isolation](https://www.postgresql.org/docs/current/transaction-iso.html), [btree_gist](https://www.postgresql.org/docs/current/btree-gist.html).

</details>
