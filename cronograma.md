# Cronograma Semanal

> Marque `[x]` conforme for concluindo cada semana.

---

## Fase 1 — Base DevOps/SRE (Semanas 1 a 4)

**Ritmo:** 1 h por dia | **Regra 1:1** — cada hora de conteúdo = 1 hora escrevendo código

### Semana 1: Python — fundamentos e como a linguagem pensa
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Variáveis, tipos, condicionais e loops |
| Ter | Funções e escopo |
| Qua | Listas, tuplas, sets e dicionários |
| Qui | Exceções, módulos e arquivos |
| Sex | venv, pacotes e orientação a objetos básica |
| **Sáb** | **Mini projeto: escolha um e construa do zero** |

**Mini projetos sugeridos:** conversor de moeda · gerenciador de tarefas no terminal · sistema simples de cadastro · leitor de arquivo · jogo no terminal

> 🧪 **Autoteste:** fecha o material, abre o arquivo vazio. Consegue escrever uma função? Um dicionário? Um loop? Se não, ainda não aprendeu — reconheceu.

> 💡 Nesse primeiro mês você não está construindo portfólio. Está construindo **fundamentos** e aprendendo a tomar decisões.

**Entrega:** mini projeto em Python funcionando.

---

### Semana 2: Git, organização de projeto e engenharia básica
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Git: init, add, commit, branches, merge, rebase |
| Ter | GitHub: push, pull, PR, issues e commits detalhados |
| Qua | Ambiente virtual, dependências e `pyproject.toml` |
| Qui | Tipagem (`type hints`), tratamento de erros e `logging` |
| Sex | Debugging (`print`, `pdb`, breakpoints) e organização de arquivos |
| **Sáb** | **Projeto estruturado com .git, README, testes e arquivos separados** |

**Projetos sugeridos:** sistema de biblioteca · controle de despesas · sistema de estoque

> ⚠️ A pergunta **"Por que eu organizei assim?"** precisa ter resposta clara. Decisões precisam ser sempre fundamentadas.

> 💡 Ninguém te contrata para escrever `for` e `if`. No mercado, você interage com projetos, toma decisões, presta suporte e revisa código dos outros.

**Entrega:** projeto pequeno com estrutura, testes, .git e readme.md.

---

### Semana 3: Docker e CI/CD
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Docker: conceitos, imagens, containers |
| Ter | Dockerfile e multi-stage builds |
| Qua | Docker Compose: múltiplos serviços |
| Qui | GitHub Actions: pipeline básica (lint + testes) |
| Sex | `pre-commit`, `ruff` e automação de qualidade |
| **Sáb** | **Pipeline CI verde rodando no repositório** |

**Entrega:** repositório com pipeline CI/CD e imagem Docker.

---

### Semana 4: Ansible, Prometheus, Grafana e SLOs
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Ansible: inventário e playbooks básicos |
| Ter | Ansible: roles e automação de configuração |
| Qua | Prometheus: métricas, scraping e PromQL |
| Qui | Grafana: dashboards e alertas |
| Sex | SLOs: conceito e definição |
| **Sáb** | **Stack de monitoramento rodando + repositório base da API** |

**Entrega:** stack de monitoramento rodando + repositório base da API de inventário.

---

## Fase 2 — Fundamentos de Backend (Semanas 5 a 8)

**Ritmo:** 1 h seg–sex + 2 h sábado

### Semana 5: Python intermediário e HTTP/REST
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Classes e orientação a objetos (herança, composição) |
| Ter | Type hints avançados e `dataclasses` |
| Qua | Estrutura de projeto (pacotes, `pyproject.toml`, `ruff`) e `logging` |
| Qui | HTTP na prática: `curl`, métodos, status codes, headers, cookies, CORS |
| Sex | REST: recursos, stateless, idempotência, versionamento |
| **Sáb** | **Desenhar o contrato da API (endpoints, entradas, saídas)** |

> 💡 Importante saber de framework, mas **mais importante ainda saber o que tem por baixo**: rotas e HTTP, ORM e SQL, sessão e auth, templates. Se não entende o que acontece por baixo, vira quem sabe repetir tutorial mas quando sai do roteiro, trava.

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
| **Sáb** | **API conectada ao Postgres + dados populados** |

> 💡 Popular o banco com dados **realistas**: usuários, serviços, horários, disponibilidade, bloqueios. Enfrentar problemas que tutoriais não mostram — ex: **dois clientes tentando agendar o mesmo horário ao mesmo tempo**. O que acontece? Quem passa na frente?

> ⚠️ O ORM não substitui entender SQL. Sempre olhe o SQL que ele gera.

**Entrega:** `docker compose up` sobe a API com banco, migrations e dados populados.

---

## Fase 3 — Backend Profissional (Semanas 9 a 12)

**Ritmo:** 1 h seg–sex + 2 h sábado

### Semana 9: Autenticação, autorização e segurança
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Hash de senha (argon2 / bcrypt) — **nunca** texto puro no código ou no banco |
| Ter | JWT: o que tem dentro, header, payload, assinatura, por que expira, o que acontece quando expira |
| Qua | Proteção de rotas e RBAC — quem pode acessar cada endpoint (admin / profissional / cliente) |
| Qui | OAuth2 / OIDC (conceitual): quem emite o token e quem valida |
| Sex | OWASP API Top 10, SQL Injection, segredos em variáveis de ambiente |
| **Sáb** | **Login funcionando + rotas protegidas por papel no agendamento** |

> ⚠️ **Sem copiar e colar.** Entenda: o que é token? O que tem dentro do JWT? Por que expira? O que acontece quando expira? Quem pode acessar cada endpoint? Login parece simples **até você precisar fazer direito**.

**Entrega:** autenticação JWT com RBAC na API.

---

### Semana 10: Testes
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | `pytest` avançado: fixtures e `parametrize` |
| Ter | Testes de API com `TestClient` |
| Qua | Banco de teste isolado (Postgres em container) |
| Qui | Mocks e cobertura (`pytest-cov`) |
| Sex | Rodar testes no GitHub Actions + `pre-commit` com `ruff` |
| **Sáb** | **Cobertura ≥ 70% e pipeline verde** |

> 💡 Testes existem para **validar comportamentos que não podem quebrar**. Teste as regras de negócio do agendamento: conflito de horário, permissões, cancelamento.

**Entrega:** suite de testes com cobertura e CI verde.

---

### Semana 11: Cache e filas
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Redis: strings, hashes e TTL |
| Ter | Cache-aside na API e invalidação |
| Qua | Rate limiting simples |
| Qui | Filas: conceito, desacoplamento, processamento assíncrono |
| Sex | RabbitMQ: produtor, consumidor, ack, filas duráveis. Kafka (conceito) |
| **Sáb** | **Endpoint com cache + worker processando fila** |

> ⚠️ **Tecnologia não é pra bonito — é pra resolver problema.**
> - Redis só entra se resolver um problema real (ex: cache de horários disponíveis)
> - Fila só se houver tarefas que fazem sentido assíncronas (ex: envio de confirmação)
> - A pergunta certa **não é** "que tecnologia está faltando?" mas sim **"que problema meu projeto tem agora?"**

**Entrega:** cache Redis e worker com fila funcionando.

---

### Semana 12: Observabilidade e produção
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Logs estruturados (JSON) com correlation id |
| Ter | Variáveis de ambiente, migrations e documentação como parte de produção |
| Qua | Endpoints `/health` e `/ready` + métricas com `prometheus-client` |
| Qui | Scrape no Prometheus + dashboard Grafana (método RED) |
| Sex | Tracing com OpenTelemetry + definir SLO e alerta |
| **Sáb** | **Dashboard e alerta da API funcionando** |

**Entrega:** observabilidade completa (logs, métricas, tracing, SLO).

---

## Fase 4 — Arquitetura, Deploy e Mercado (Semanas 13 a 16)

**Ritmo:** 1 h seg–sex + 2 h sábado

### Semana 13: Arquitetura
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Monólito modular vs microserviços (e **quando não usar** microserviços) |
| Ter | 12-factor app |
| Qua | Comunicação: REST, gRPC, eventos |
| Qui | Resiliência: retry com backoff, circuit breaker, saga (conceito) |
| Sex | Clean Code, SOLID, gRPC "hello world" em Python |
| **Sáb** | **Diagrama de arquitetura + ADR** |

**Entrega:** diagrama e ADR documentando decisões.

---

### Semana 14: Deploy em Kubernetes / OpenShift
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Imagem enxuta e sem root |
| Ter | Deployment, Service, Route/Ingress |
| Qua | ConfigMap e Secret |
| Qui | Probes (liveness/readiness) com `/health` |
| Sex | Requests/limits, rollout, rollback, blue-green e canary (conceito) |
| **Sáb** | **API rodando no cluster + pipeline/GitOps** |

> ⚠️ Use sempre um cluster de **laboratório**, nunca o de produção.

**Entrega:** API deployada no cluster de lab com atualização automatizada.

---

### Semana 15: Algoritmos, system design e treino de entrevista
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Big-O, listas, dicionários, pilhas, filas |
| Ter | Busca binária, árvores e heaps |
| Qua | Padrões: two pointers, sliding window |
| Qui | System design: encurtador de URL, rate limiter, cache |
| Sex | Escalabilidade de banco: réplicas, índices, sharding |
| **Sáb** | **10 problemas resolvidos + 1 system design + simulação de entrevista** |

> 🎤 **Treino de entrevista.** Use IA como entrevistador de backend Python. Perguntas-modelo:
> - Por que FastAPI e não Django/Flask?
> - Por que PostgreSQL?
> - Como você evitaria dois agendamentos simultâneos no mesmo horário?
> - Qual a diferença entre autenticação e autorização?
> - O que acontece quando essa transação falha?
> - Por que você colocou esse índice?
>
> Se travar, anote o ponto fraco. Use flashcards para revisar: é conceito que falta ou prática de código?

**Entrega:** exercícios resolvidos, system design escrito e pontos fracos mapeados.

---

### Semana 16: Projeto final, portfólio e candidatura
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | README profissional do projeto de agendamento (ver estrutura abaixo) |
| Ter | Polir repositórios (CI verde, ADRs, diagrama) |
| Qua | Currículo e LinkedIn — narrativa "infra → plataforma/backend" |
| Qui | GitHub profile README + pesquisa de vagas reais |
| Sex | Perguntas comportamentais (STAR) + simulação final de entrevista |
| **Sáb** | **Repositórios publicados + currículo atualizado + primeiras candidaturas** |

> 📋 **Estrutura do README profissional:**
> 1. Que problema esse sistema resolve?
> 2. Regras de negócio
> 3. Como rodar
> 4. Arquitetura
> 5. Decisões importantes — *Por que PostgreSQL? Por que essa estrutura? Como evito conflito? Como organizei autenticação?*
> 6. Desafios encontrados
> 7. Testes
> 8. Documentação
> 9. Referências
> 10. Demo online
>
> A ideia é deixar claras as **evidências do raciocínio**, não apenas uma pasta com código.

> 🔄 **Não espere terminar para se candidatar.** Candidatura é um loop: ajusta currículo → entrevista → recebe feedback → estuda → aplica novamente.

**Entrega:** portfólio completo, currículo pronto e candidaturas em andamento.
