# Recursos e Materiais

> Todos os links e materiais do plano, organizados por semana.
> Legenda: 📖 Documentação · 🏋️ Exercícios · 🔧 Ferramenta

---

## 📌 Projeto principal: Sistema de Agendamento

O projeto que vai acompanhar você do meio ao fim do plano. Comece a pensar nele desde cedo e implemente-o gradualmente a partir da Semana 7.

**Links úteis para inspiração de regras de negócio:**
- 📖 [Calendly — Como funciona](https://calendly.com/features) — fluxo de agendamento, disponibilidade, notificações
- 📖 [Google Calendar API — Concepts](https://developers.google.com/calendar/api/concepts) — modelagem de eventos, recorrência, fusos horários
- 📖 [Cal.com (open-source)](https://github.com/calcom/cal.com) — código-fonte de um sistema de agendamento real para referência
- 📖 [Doctolib-like Booking Flow](https://www.doctolib.fr/) — exemplo de agendamento com regras de negócio em saúde

---

## Fase 1 — Base DevOps/SRE

### Semana 1: Python para automação
- 📖 [Tutorial oficial do Python](https://docs.python.org/3/tutorial/)
- 📖 [WSL2 — Documentação Microsoft](https://learn.microsoft.com/windows/wsl/)
- 📖 [Python — venv](https://docs.python.org/3/library/venv.html)
- 🏋️ **Mini projetos sugeridos:** conversor de moeda, gerenciador de tarefa no terminal, sistema de cadastro, leitor de arquivo, jogo no terminal

### Semana 2: Git, CI/CD e Docker
- 📖 [Pro Git Book (gratuito)](https://git-scm.com/book/pt-br/v2)
- 📖 [GitHub Actions — Docs](https://docs.github.com/actions)
- 📖 [Docker — Get Started](https://docs.docker.com/get-started/)
- 📖 [Dockerfile — Best Practices (multi-stage)](https://docs.docker.com/build/building/best-practices/)
- 📖 [Python — Debugging (pdb)](https://docs.python.org/3/library/pdb.html)
- 📖 [Python — Logging](https://docs.python.org/3/howto/logging.html)
- 📖 [Python — Type Hints](https://docs.python.org/3/library/typing.html)
- 🏋️ **Projetos sugeridos:** sistema de biblioteca, controle de despesas, sistema de estoque

### Semana 3: Ansible
- 📖 [Ansible — Getting Started](https://docs.ansible.com/ansible/latest/getting_started/)

### Semana 4: Prometheus, Grafana e SLOs
- 📖 [Prometheus — Docs](https://prometheus.io/docs/)
- 📖 [Grafana — Docs](https://grafana.com/docs/grafana/latest/)
- 📖 [SRE Workbook — SLOs](https://sre.google/workbook/table-of-contents/)

---

## Fase 2 — Fundamentos de Backend

### Semana 5: Python intermediário e HTTP/REST
- 📖 [Python — Classes (tutorial oficial)](https://docs.python.org/3/tutorial/classes.html)
- 📖 [Python — typing](https://docs.python.org/3/library/typing.html)
- 📖 [MDN — HTTP](https://developer.mozilla.org/docs/Web/HTTP)
- 📖 [HTTP — MDN Status Codes](https://developer.mozilla.org/docs/Web/HTTP/Status)
- 📖 [Microsoft API Guidelines](https://github.com/microsoft/api-guidelines)

> **Nota:** Entenda o que está por baixo do framework: rotas, HTTP, ORM/SQL, sessão, auth. Antes de usar FastAPI ou qualquer framework, saiba o que ele abstrai.

### Semana 6: SQL e PostgreSQL
- 📖 [PostgreSQL — Tutorial](https://www.postgresql.org/docs/current/tutorial.html)
- 🏋️ [pgExercises](https://pgexercises.com/)
- 📖 [Use The Index, Luke](https://use-the-index-luke.com/)
- 🔧 [dbdiagram.io](https://dbdiagram.io/) — diagrama ER

> **Nota:** Estude SQL puro antes do ORM. Entenda o que o ORM abstrai.

### Semana 7: FastAPI e Pydantic
- 📖 [FastAPI — Tutorial](https://fastapi.tiangolo.com/tutorial/)
- 📖 [Pydantic — Concepts](https://docs.pydantic.dev/latest/concepts/models/)
- 📖 [FastAPI — Middleware](https://fastapi.tiangolo.com/tutorial/middleware/)

> **Nota:** Este é um bom momento para iniciar o **Projeto de Agendamento**. Comece com os endpoints básicos (CRUD de compromissos) e evolua nas semanas seguintes.

### Semana 8: SQLAlchemy e Alembic
- 📖 [SQLAlchemy 2.0 — Tutorial](https://docs.sqlalchemy.org/en/20/tutorial/)
- 📖 [Alembic — Tutorial](https://alembic.sqlalchemy.org/en/latest/tutorial.html)
- 📖 [FastAPI — SQL Databases](https://fastapi.tiangolo.com/tutorial/sql-databases/)

---

## Fase 3 — Backend Profissional

### Semana 9: Autenticação, autorização e segurança
- 📖 [FastAPI — Security](https://fastapi.tiangolo.com/tutorial/security/)
- 📖 [JWT.io — Introduction](https://jwt.io/introduction)
- 📖 [OAuth.com (gratuito)](https://www.oauth.com/)
- 📖 [OWASP API Security](https://owasp.org/API-Security/)
- 📖 [OWASP — Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)

### Semana 10: Testes
- 📖 [pytest — Docs](https://docs.pytest.org/)
- 📖 [FastAPI — Testing](https://fastapi.tiangolo.com/tutorial/testing/)
- 📖 [pytest-cov](https://pytest-cov.readthedocs.io/)
- 🔧 [pre-commit](https://pre-commit.com/)

### Semana 11: Cache e filas
- 📖 [Redis — Docs](https://redis.io/docs/)
- 🏋️ [Redis University (cursos gratuitos)](https://university.redis.io/)
- 📖 [RabbitMQ — Tutorials (1 a 3 em Python)](https://www.rabbitmq.com/tutorials)
- 📖 [Kafka — Introdução](https://kafka.apache.org/intro)

### Semana 12: Observabilidade na aplicação
- 📖 [Python — Logging HOWTO](https://docs.python.org/3/howto/logging.html)
- 📖 [prometheus-client (Python)](https://prometheus.github.io/client_python/)
- 📖 [OpenTelemetry — Python](https://opentelemetry.io/docs/languages/python/)
- 📖 [SRE Workbook — SLOs](https://sre.google/workbook/table-of-contents/)

---

## Fase 4 — Arquitetura, Deploy e Mercado

### Semana 13: Arquitetura
- 📖 [12-Factor App](https://12factor.net/)
- 📖 [Microservices.io — Catálogo de padrões](https://microservices.io/)
- 📖 [Martin Fowler — Microservices](https://martinfowler.com/articles/microservices.html)
- 📖 [gRPC — Python Quickstart](https://grpc.io/docs/languages/python/quickstart/)

### Semana 14: Deploy em Kubernetes / OpenShift
- 📖 [Kubernetes — Workloads](https://kubernetes.io/docs/concepts/workloads/)
- 📖 [OpenShift — Docs](https://docs.redhat.com/)
- 🔧 [Developer Sandbox for Red Hat OpenShift (gratuito)](https://developers.redhat.com/developer-sandbox)
- 📖 [Argo CD — Docs](https://argo-cd.readthedocs.io/)

### Semana 15: Algoritmos e system design
- 🏋️ [NeetCode Roadmap](https://neetcode.io/roadmap) — comece pelos Easy
- 🔧 [VisuAlgo](https://visualgo.net/) — visualização de algoritmos
- 📖 [System Design Primer](https://github.com/donnemartin/system-design-primer)
- 🏋️ **Simulação de entrevista:** use uma IA (ChatGPT, Gemini etc.) como entrevistador de backend Python. Peça para ela fazer perguntas técnicas e avalie suas respostas.
- 📖 **Perguntas-modelo para praticar:**
  - "Explique o GIL do Python e quando ele importa."
  - "Como você projetaria uma API de agendamento com controle de concorrência?"
  - "Qual a diferença entre autenticação e autorização? Dê exemplos com JWT/OAuth."
  - "Descreva o fluxo de um request HTTP desde o navegador até o banco de dados."
  - "Como você garantiria a escalabilidade de um serviço com filas e cache?"

### Semana 16: Portfólio e entrevistas
- 📖 [roadmap.sh/backend](https://roadmap.sh/backend) — conferir lacunas
- 📖 [GitHub — Profile README](https://docs.github.com/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme)
- 📖 **Estrutura de README profissional** — use este template nos seus projetos:
  - **Título e descrição** — o que o projeto faz, em uma frase
  - **Tech stack** — linguagens, frameworks, banco de dados
  - **Como rodar** — pré-requisitos, instalação, variáveis de ambiente
  - **Endpoints / Funcionalidades** — tabela ou lista dos principais endpoints
  - **Arquitetura** — diagrama ou descrição das camadas
  - **Testes** — como rodar, cobertura
  - **Deploy** — onde está hospedado, CI/CD
  - **Licença e contato**

> **Nota:** Candidatura é um loop, não um evento único. Refine currículo, portfólio e abordagem a cada feedback recebido. Itere continuamente.

---

## Pós-plano (opcional)

- 📖 [Node.js — Learn](https://nodejs.org/learn) + [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/)
- 📖 [Go Tour](https://go.dev/tour/) + [Go by Example](https://gobyexample.com/)
