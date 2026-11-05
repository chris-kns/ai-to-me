# Cronograma Semanal

> Marque `[x]` conforme for concluindo cada semana.

---

## Fase 1 — Base DevOps/SRE (Semanas 1 a 4)

**Ritmo:** 1 h por dia

### Semana 1: Python para automação
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg–Sex | Python básico para automação com WSL2 |
| Sáb | Mini projeto de automação |

**Entrega:** mini projeto em Python funcionando.

---

### Semana 2: Git, CI/CD e Docker
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg–Ter | Git: branches, merge, rebase |
| Qua–Qui | GitHub Actions: pipeline básica |
| Sex–Sáb | Docker: Dockerfile multi-stage, build e push |

**Entrega:** repositório com pipeline CI/CD e imagem Docker.

---

### Semana 3: Ansible
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg–Sáb | Inventário, playbooks, roles e automação de configuração |

**Entrega:** playbook Ansible funcional.

---

### Semana 4: Prometheus, Grafana e SLOs (dias 22–30)
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg–Qua | Prometheus: métricas, scraping, PromQL |
| Qui–Sex | Grafana: dashboards e alertas |
| Sáb | SLOs, fechamento da fase e preparação da base da API |

**Entrega:** stack de monitoramento rodando + repositório base da API.

---

## Fase 2 — Fundamentos de Backend (Semanas 5 a 8)

**Ritmo:** 1 h seg–sex + 2 h sábado

### Semana 5: Python intermediário e HTTP/REST
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Classes e orientação a objetos básica |
| Ter | Type hints e `dataclasses` |
| Qua | Estrutura de projeto (pacotes, `pyproject.toml`, `ruff`) e `logging` |
| Qui | HTTP: `curl`, métodos, status codes, headers, cookies, CORS |
| Sex | REST: recursos, stateless, idempotência, versionamento |
| **Sáb** | **Desenhar o contrato da API (endpoints, entradas, saídas)** |

**Entrega:** contrato da API de inventário documentado.

---

### Semana 6: SQL e PostgreSQL
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Postgres em Docker + `psql` |
| Ter | Modelagem ER e normalização do inventário |
| Qua | CRUD, `JOIN`, `GROUP BY`, `HAVING` |
| Qui | Índices e `EXPLAIN ANALYZE` |
| Sex | Transações, ACID, backup e restore (`pg_dump` / `pg_restore`) |
| **Sáb** | **Schema + dados de exemplo + 10 consultas úteis** |

**Entrega:** banco modelado com dados e consultas.

---

### Semana 7: FastAPI e Pydantic
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Primeira rota e `/docs` |
| Ter | Parâmetros de path e query |
| Qua | Modelos Pydantic (entrada e saída) |
| Qui | Validação e tratamento de erros |
| Sex | `Depends`, routers e `async` vs síncrono |
| **Sáb** | **CRUD do inventário em memória com validação** |

**Entrega:** API CRUD em memória rodando.

---

### Semana 8: SQLAlchemy e Alembic
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | SQLAlchemy 2.0: engine, session, models |
| Ter | Relacionamentos (site → servidor → serviço) |
| Qua | Sessão por requisição via `Depends` |
| Qui | Migrations com Alembic |
| Sex | Docker Compose (API + Postgres) |
| **Sáb** | **API conectada ao Postgres + migrations versionadas** |

**Entrega:** `docker compose up` sobe a API com banco e migrations.

---

## Fase 3 — Backend Profissional (Semanas 9 a 12)

**Ritmo:** 1 h seg–sex + 2 h sábado

### Semana 9: Autenticação, autorização e segurança
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Hash de senha (argon2 / bcrypt) |
| Ter | JWT: header, payload, assinatura, expiração, refresh |
| Qua | Proteção de rotas e RBAC (admin / leitor) |
| Qui | OAuth2 / OIDC (conceitual) |
| Sex | OWASP API Top 10, SQL Injection, segredos em env vars |
| **Sáb** | **Login funcionando + rotas protegidas por papel** |

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

**Entrega:** cache Redis e worker com fila funcionando.

---

### Semana 12: Observabilidade na aplicação
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Logs estruturados (JSON) com correlation id |
| Ter | Endpoints `/health` e `/ready` |
| Qua | Métricas com `prometheus-client` (`/metrics`) |
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
| Seg | Monólito modular vs microserviços |
| Ter | 12-factor app |
| Qua | Comunicação: REST, gRPC, eventos |
| Qui | Resiliência: retry, circuit breaker, saga |
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
| Sex | Requests/limits, rollout, rollback, blue-green e canary |
| **Sáb** | **API rodando no cluster + pipeline/GitOps** |

**Entrega:** API deployada no cluster de lab com atualização automatizada.

---

### Semana 15: Estrutura de dados, algoritmos e system design
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Big-O, listas, dicionários, pilhas, filas |
| Ter | Busca binária, árvores e heaps |
| Qua | Two pointers, sliding window |
| Qui | System design: encurtador de URL, rate limiter, cache |
| Sex | Escalabilidade de banco: réplicas, índices, sharding |
| **Sáb** | **10 problemas resolvidos + 1 system design** |

**Entrega:** exercícios resolvidos e system design escrito.

---

### Semana 16: Projeto final, portfólio e entrevistas
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | README profissional: como rodar, arquitetura, decisões |
| Ter | Polir repositório (CI verde, ADRs, diagrama) |
| Qua | Currículo e LinkedIn — narrativa "infra → plataforma/backend" |
| Qui | GitHub profile README |
| Sex | Perguntas comportamentais (STAR) + simulação de entrevista |
| **Sáb** | **Repositório final publicado + currículo atualizado** |

**Entrega:** portfólio completo e currículo pronto.
