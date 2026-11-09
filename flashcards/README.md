# Flashcards

Método para transformar ponto fraco em conhecimento. A pergunta que guia tudo: **o que falta é conceito, prática de código ou decisão?**

## Os três tipos

| Tipo | Quando usar | Como o cartão é |
|------|-------------|-----------------|
| **C — Conceito** | Não sei explicar o que é | "O que é...?" / "Qual a diferença entre...?" |
| **P — Prática** | Sei explicar, mas travo ao escrever | "Escreva a query/função/Dockerfile que..." (resposta é código) |
| **D — Decisão** | Sei fazer, mas não sei justificar | "Por que você escolheu...?" |

## Fluxo

1. **Capture:** toda vez que travar (estudo, exercício, mini-entrevista), registre em [pontos-fracos.md](pontos-fracos.md) com o tipo (C/P/D).
2. **Transforme:** peça ao agente `/flashcards` (ou use o [prompt](../agente/prompts/gerador-de-flashcards.md)). Máximo de 10 cartões por sessão.
3. **Revise com caixas (Leitner):**

| Caixa | Frequência | Regra |
|-------|------------|-------|
| 1 | Todo dia | Errou, volta para a caixa 1 |
| 2 | A cada 3 dias | Acertou 1 vez, sobe |
| 3 | 1 vez por semana | Acertou 3 vezes seguidas, está dominado |

4. **Feche o ciclo:** cartão dominado vira uma linha de "Status: ok" em `pontos-fracos.md`. Se o mesmo ponto volta 3 vezes, pare de revisar e **volte ao conteúdo** com outra abordagem (um diagrama, um experimento, uma explicação em voz alta).

## Regras

- Responda **antes** de olhar a resposta. Sem exceção.
- Tipo P: escreva de verdade, em um arquivo vazio.
- Tipo D: responda em voz alta, como se estivesse na entrevista.
- 10 minutos por dia valem mais do que 1 hora no fim de semana.

## Arquivos

- [pontos-fracos.md](pontos-fracos.md): o que travou e o status
- [banco-de-perguntas.md](banco-de-perguntas.md): perguntas de entrevista com resposta-base, por tema
