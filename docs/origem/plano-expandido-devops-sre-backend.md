# Plano de estudos expandido: DevOps/SRE + Backend Engineer

*Cerca de 16 semanas, com um único projeto como fio condutor.*

## Meu objetivo

Em cerca de **16 semanas (uns 4 meses)**, montar o perfil que mais valoriza quem vem de infraestrutura: **alguém que domina a infra e também constrói, testa e opera uma aplicação backend de ponta a ponta.**

Isso é mais forte do que ser só DevOps ou só Backend júnior, porque poucas pessoas reúnem os dois lados.

O fio condutor é **um único projeto**: uma **API de inventário de infraestrutura** (servidores, sites, serviços), um domínio que você já conhece bem. Ela nasce com o mini projeto da semana 1, ganha banco, autenticação, testes, cache e filas, e termina rodando num cluster com CI/CD e monitoramento. Tudo vai para o GitHub como portfólio.

## Visão geral e ritmo

| Fase | Quando | Tema |
| --- | --- | --- |
| 1. Base DevOps/SRE | Dias 1 a 30 (semanas 1 a 4) | Python, Git, CI/CD, Docker, Ansible, Prometheus/Grafana |
| 2. Fundamentos de Backend | Semanas 5 a 8 | Python intermediário, HTTP/REST, PostgreSQL, FastAPI, SQLAlchemy |
| 3. Backend profissional | Semanas 9 a 12 | Autenticação e segurança, testes, Redis e filas, observabilidade na aplicação |
| 4. Arquitetura, deploy e mercado | Semanas 13 a 16 | Arquitetura, Kubernetes/OpenShift, algoritmos, portfólio e entrevistas |

**Ritmo:**

- **Fase 1:** 1h por dia.
- **Fases 2 a 4:** 1h de segunda a sexta (teoria e exercícios) e **2h no sábado** (a entrega da semana). Domingo livre. São cerca de 7h por semana, e o sábado é onde o conhecimento vira projeto.
- Se não der para estudar no sábado, some umas 3 a 4 semanas ao total.

## Fase 1: Base DevOps/SRE (dias 1 a 30)

- **Semana 1:** Python para automação (com WSL2 no lugar do CMD)
- **Semana 2:** Git, CI/CD com GitHub Actions e Docker (multi-stage)
- **Semana 3:** Ansible
- **Semana 4 (dias 22 a 30):** Prometheus, Grafana, SLOs e fechamento

O repositório do mini projeto da semana 4 é a **base da API** que você vai construir a partir de agora.

## Fase 2: Fundamentos de Backend

### Semana 5: Python intermediário e HTTP/REST

**Ordem de estudo**

1. Classes e orientação a objetos básica
2. Type hints e `dataclasses`
3. Estrutura de projeto (pacotes, `pyproject.toml`, `ruff`) e o módulo `logging`
4. HTTP na prática: `curl`, métodos, status codes, headers, cookies e CORS
5. Princípios REST: recursos, stateless, idempotência e versionamento

**Entrega (sábado):** desenhar o contrato da API de inventário (lista de endpoints, entradas e saídas).

**Materiais**

- docs.python.org/3/tutorial (capítulo de Classes) e docs.python.org/3/library/typing.html
- MDN HTTP: developer.mozilla.org/docs/Web/HTTP (a melhor referência gratuita)
- Guia de design de APIs: github.com/microsoft/api-guidelines

### Semana 6: SQL e PostgreSQL

Você já conhece MySQL e SQL Server, então foque no que é **específico do Postgres**: tipos, `JSONB`, schemas, roles e `psql`.

**Ordem de estudo**

1. Subir o Postgres em Docker e usar o `psql`
2. Modelagem ER e normalização do inventário
3. CRUD, `JOIN`, `GROUP BY` e `HAVING`
4. **Índices e `EXPLAIN ANALYZE`** (é o que mais pesa na prática)
5. Transações e ACID
6. Backup e restore com `pg_dump` e `pg_restore`

**Entrega:** schema + dados de exemplo + 10 consultas úteis.

**Materiais**

- postgresql.org/docs/current/tutorial.html
- pgexercises.com (exercícios grátis)
- use-the-index-luke.com (índices explicados de forma excelente, grátis)
- dbdiagram.io para desenhar o diagrama ER

### Semana 7: FastAPI e Pydantic

**Ordem de estudo**

1. Primeira rota e documentação automática (`/docs`)
2. Parâmetros de path e query
3. Modelos Pydantic de entrada e saída
4. Validação e tratamento de erros
5. Injeção de dependências (`Depends`) e organização em routers
6. Conceito de `async` vs síncrono

**Entrega:** CRUD do inventário em memória, com validação.

**Materiais**

- fastapi.tiangolo.com/tutorial (siga na ordem, é muito bem escrito)
- docs.pydantic.dev (Concepts: Models, Validators)

### Semana 8: Persistência com SQLAlchemy e Alembic

**Ordem de estudo**

1. SQLAlchemy 2.0: engine, session e models
2. Relacionamentos (site → servidor → serviço)
3. Sessão por requisição via `Depends`
4. Migrations com Alembic
5. Docker Compose (API + Postgres)
6. Paginação e filtros

**Entrega:** API conectada ao Postgres rodando por `docker compose up`, com migrations versionadas.

**Materiais**

- docs.sqlalchemy.org/en/20/tutorial
- alembic.sqlalchemy.org/en/latest/tutorial.html
- fastapi.tiangolo.com/tutorial/sql-databases

**Dica:** o ORM não substitui entender SQL. Sempre olhe o SQL que ele gera.

## Fase 3: Backend profissional

### Semana 9: Autenticação, autorização e segurança

**Ordem de estudo**

1. Hash de senha (argon2 ou bcrypt), nunca criptografia reversível
2. Login e **JWT**: header, payload, assinatura, expiração e refresh
3. Proteção de rotas e **RBAC** (papéis admin/leitor)
4. OAuth2/OIDC em nível conceitual: quem emite o token e quem valida
5. **OWASP API Security Top 10** (autorização quebrada, mass assignment, etc.)
6. SQL Injection e por que usar queries parametrizadas
7. Segredos via variáveis de ambiente, nunca no código

**Entrega:** login funcionando e rotas protegidas por papel.

**Materiais**

- fastapi.tiangolo.com/tutorial/security
- jwt.io/introduction
- oauth.com (guia gratuito de OAuth 2.0 do Aaron Parecki)
- owasp.org/API-Security e cheatsheetseries.owasp.org (veja *Password Storage*)

### Semana 10: Testes

**Ordem de estudo**

1. `pytest` avançado: fixtures e `parametrize`
2. Testes de API com `TestClient`
3. Banco de teste isolado (Postgres em container)
4. Mocks e cobertura (`pytest-cov`)
5. Rodar tudo no GitHub Actions
6. `pre-commit` com `ruff`

**Entrega:** cobertura realista (70% ou mais) e pipeline verde.

**Materiais**

- docs.pytest.org
- fastapi.tiangolo.com/tutorial/testing
- pytest-cov.readthedocs.io e pre-commit.com

### Semana 11: Cache e filas

**Ordem de estudo**

1. Redis: strings, hashes e TTL
2. Padrão **cache-aside** na API e como invalidar cache
3. Rate limiting simples
4. Por que usar filas: desacoplamento e processamento assíncrono
5. **RabbitMQ:** produtor, consumidor, ack e filas duráveis
6. **Kafka** só no conceito (topic, partition, consumer group)
7. Consumidores idempotentes

**Entrega:** um endpoint com cache e um worker que processa tarefas vindas de uma fila.

**Materiais**

- redis.io/docs e university.redis.io (cursos gratuitos)
- rabbitmq.com/tutorials (tutoriais 1 a 3 em Python)
- kafka.apache.org/intro (leitura conceitual)

### Semana 12: Observabilidade na aplicação

É aqui que as duas trilhas se encontram. Você instrumenta a API e monitora com a stack da semana 4.

**Ordem de estudo**

1. Logs estruturados em JSON com correlation id
2. Endpoints `/health` e `/ready`
3. Métricas com `prometheus-client` (`/metrics`): contadores e histogramas
4. Scrape no seu Prometheus + dashboard Grafana no método **RED** (taxa, erros, duração)
5. Tracing básico com OpenTelemetry
6. Definir um **SLO** para a API (ex.: 99% das requisições abaixo de 300 ms) e um alerta

**Entrega:** dashboard e alerta da API funcionando.

**Materiais**

- docs.python.org/3/howto/logging.html
- prometheus.github.io/client\_python
- opentelemetry.io/docs/languages/python
- sre.google/workbook/table-of-contents (capítulo de SLOs)

## Fase 4: Arquitetura, deploy e mercado

### Semana 13: Arquitetura

**Ordem de estudo**

1. Monólito modular vs microserviços, incluindo **quando não usar** microserviços
2. **12-factor app**
3. Comunicação: REST, gRPC e eventos
4. Padrões de resiliência: retry com backoff, circuit breaker e saga (conceito)
5. Clean Code e SOLID no essencial: funções pequenas, camadas separadas e injeção de dependência
6. gRPC “hello world” em Python

**Entrega:** diagrama de arquitetura + um ADR (registro de decisão) explicando suas escolhas.

**Materiais**

- 12factor.net
- microservices.io (catálogo de padrões)
- martinfowler.com/articles/microservices.html
- grpc.io/docs/languages/python/quickstart

### Semana 14: Deploy em Kubernetes/OpenShift

Aqui sua experiência com OCP4 vira diferencial: você faz o deploy que a maioria dos devs não sabe fazer.

**Ordem de estudo**

1. Imagem enxuta e **sem root**. O OpenShift roda containers com UID arbitrário, então a imagem precisa funcionar assim.
2. Deployment, Service e Route/Ingress
3. ConfigMap e Secret
4. Probes (liveness/readiness) usando o `/health` da semana 12
5. Requests/limits, rollout e rollback
6. Blue-green e canary (conceito)
7. GitOps com Argo CD / OpenShift GitOps

**Entrega:** a API rodando no cluster de laboratório e atualizada via pipeline ou GitOps.

**Materiais**

- kubernetes.io/docs/concepts/workloads
- Documentação do OpenShift: docs.redhat.com
- **Developer Sandbox for Red Hat OpenShift** (cluster gratuito para estudo): developers.redhat.com/developer-sandbox
- argo-cd.readthedocs.io

**Atenção:** use sempre um cluster de laboratório, nunca o de produção.

### Semana 15: Estrutura de dados, algoritmos e system design

Mantenha leve. Para vagas de DevOps/SRE isso pesa pouco. Para vagas de backend pesa mais, então aumente se esse for seu alvo.

**Ordem de estudo**

1. Big-O, listas, dicionários, pilhas e filas
2. Busca binária e noção de árvores e heaps
3. Padrões de resolução (two pointers, sliding window)
4. System design básico: encurtador de URL, rate limiter e cache
5. Escalabilidade de banco: réplicas, índices e noção de sharding

**Entrega:** 10 problemas resolvidos e um system design escrito.

**Materiais**

- neetcode.io/roadmap (comece pelos Easy)
- visualgo.net (visualização de algoritmos)
- github.com/donnemartin/system-design-primer

### Semana 16: Projeto final, portfólio e entrevistas

**Ordem de estudo**

1. README profissional: como rodar, arquitetura e decisões
2. Polir o repositório (CI verde, ADRs e diagrama)
3. Currículo, GitHub e LinkedIn contando a história **“infra → plataforma/backend”**, com sua experiência real em datacenter, redes e Kubernetes em destaque
4. Perguntas comportamentais (método STAR)
5. Simulação de entrevista de troubleshooting e de system design

**Entrega:** repositório final publicado e currículo atualizado.

**Materiais**

- roadmap.sh/backend (para conferir lacunas)
- docs.github.com (seção de profile README)

## O que ficou de fora e por quê

O plano do PDF tinha **Node.js/TypeScript e Go**. Deixei de fora de propósito:

- **Uma linguagem bem dominada vale mais que três superficiais.** Python cobre automação e backend.
- **Node/TypeScript:** só vale se as vagas que você quer pedirem. Referências: nodejs.org/learn e typescriptlang.org/docs/handbook.
- **Go:** é o mais estratégico para infra e SRE (Kubernetes e Prometheus são escritos em Go). Estude depois da semana 16: go.dev/tour e gobyexample.com.

Se algum sábado falhar, não acumule. Retome do ponto onde parou, porque a semana 16 tem folga para absorver atraso.
