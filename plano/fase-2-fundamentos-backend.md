# Fase 2 — Fundamentos de Backend (Semanas 5 a 8)

> ← [Voltar ao plano](README.md) · Marque `[x]` ao concluir cada semana.

**Ritmo:** 1 h seg–sex + 2 h sábado

### Semana 5: Python intermediário e HTTP/REST
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Classes e orientação a objetos (herança, composição) |
| Ter | Type hints avançados e `dataclasses` |
| Qua | Estrutura de projeto em camadas (routers / services / repositories) e configuração via variáveis de ambiente (`pydantic-settings`) |
| Qui | HTTP na prática: `curl`, métodos, status codes, headers, cookies, CORS |
| Sex | REST: recursos, stateless, idempotência, versionamento |
| **Sáb** | **Desenhar o contrato da API (endpoints, entradas, saídas)** |

> 🔎 **Tarefa de mercado (40 min, em qualquer dia desta semana):** colete 15 a 20 vagas reais da sua região (DevOps, SRE, Backend Python) e preencha [mercado/analise-de-vagas.md](../mercado/analise-de-vagas.md). Decida com dados: FastAPI vs Django/Flask, Postgres, Docker, Kubernetes, qual cloud.

> 💡 Importante saber de framework, mas **mais importante ainda saber o que tem por baixo**: rotas e HTTP, ORM e SQL, sessão e auth, templates. Se não entende o que acontece por baixo, vira quem sabe repetir tutorial mas quando sai do roteiro, trava.

Mapa do que existe por baixo de cada recurso do framework: [fundamentos/por-baixo-do-framework.md](../fundamentos/por-baixo-do-framework.md)

**Entrega:** contrato da API de inventário documentado.

---

### Semana 6: SQL e PostgreSQL
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Postgres em Docker + `psql` |
| Ter | Modelagem ER e normalização do inventário |
| Qua | CRUD, `JOIN`, `GROUP BY`, `HAVING` |
| Qui | `PRIMARY KEY`, `FOREIGN KEY`, `CONSTRAINT`, índices e `EXPLAIN ANALYZE` |
| Sex | Transações, ACID, backup e restore (`pg_dump` / `pg_restore`) |
| **Sáb** | **Schema + dados de exemplo + 10 consultas úteis** |

> ⚠️ **SQL puro ANTES do ORM.** `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `JOIN`, relacionamentos, índices, transações, modelagem — tudo isso precisa estar sólido. ORM só na semana seguinte, quando fica claro **o que ele está abstraindo**.

> 🐘 **Atalho para quem já conhece MySQL/SQL Server:** a modelagem e o SQL você já domina. Concentre-se no que é específico do Postgres: `timestamptz`, `JSONB`, `ENUM`, schemas, roles, `RETURNING` e `EXPLAIN (ANALYZE, BUFFERS)`.

**Entrega:** banco modelado com dados e consultas.

---

### Semana 7: FastAPI, Pydantic e início do projeto principal
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Primeira rota e `/docs` — entender que está **expondo um endpoint HTTP** |
| Ter | Parâmetros de path, query e modelos Pydantic |
| Qua | Validação, tratamento de erros e middlewares |
| Qui | `Depends`, routers e `async` vs síncrono |
| Sex | Modelar o **sistema de agendamento**: regras de negócio, endpoints, entidades |
| **Sáb** | **CRUD do inventário em memória + estrutura inicial do agendamento** |

> 🚀 **Início do projeto principal — Sistema de Agendamento.** Não é um CRUD simples. Regras reais:
> - Usuário não pode agendar horário já ocupado
> - Horários de funcionamento configuráveis
> - Políticas de cancelamento
> - Bloqueio de agenda do profissional
> - Perfis: **cliente**, **profissional**, **admin**
> - Fuso horário: guardar em UTC (`timestamptz`) e exibir no fuso do estabelecimento (`zoneinfo`)
> - Duração por serviço e intervalo entre atendimentos
>
> Rascunho das regras e perguntas em aberto: [projetos/agendamento-api/regras-de-negocio.md](../projetos/agendamento-api/regras-de-negocio.md)
>
> Crie necessidades, questione cenários, defina regras de negócio. É aqui que o projeto ganha valor.

**Entrega:** API CRUD em memória rodando + modelagem do agendamento.

---

### Semana 8: SQLAlchemy, Alembic e persistência
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | SQLAlchemy 2.0: engine, session e models |
| Ter | Relacionamentos (site → servidor → serviço / usuário → agendamento → serviço) |
| Qua | Sessão por requisição via `Depends` |
| Qui | Migrations com Alembic |
| Sex | Docker Compose (API + Postgres) e paginação/filtros |
| **Sáb** | **API conectada ao Postgres + dados populados + experimento de concorrência** |

> 💡 Popular o banco com dados **realistas**: usuários, serviços, horários, disponibilidade, bloqueios. Enfrentar problemas que tutoriais não mostram — ex: **dois clientes tentando agendar o mesmo horário ao mesmo tempo**. O que acontece? Quem passa na frente?

> 🧨 **Experimento de concorrência (sábado):**
> 1. Escreva um script que dispare 2 requisições simultâneas para o mesmo horário e prove que **as duas passam** (double booking).
> 2. Corrija com uma garantia do **banco**, não só do código. Compare `SELECT ... FOR UPDATE`, constraint de exclusão (`EXCLUDE USING gist` + `tstzrange`, requer a extensão `btree_gist`) e níveis de isolamento.
> 3. Registre a escolha em um ADR. Detalhes: [cenários de concorrência](../projetos/agendamento-api/cenarios-de-concorrencia.md).

> ⚠️ O ORM não substitui entender SQL. Sempre olhe o SQL que ele gera.

**Entrega:** `docker compose up` sobe a API com banco, migrations e dados populados. Double booking reproduzido e impedido, com a decisão registrada em ADR.
