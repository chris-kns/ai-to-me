# Plano de estudos: visão geral

> Índice do plano de 16 semanas. O detalhe dia a dia está nos arquivos de cada fase.

## Fases

| Fase | Semanas | Tema | Arquivo |
|------|---------|------|---------|
| 1 — Base DevOps/SRE | 1 a 4 | Python, Git, Docker, CI/CD, Ansible, Prometheus/Grafana, SLOs | [fase-1-base-devops-sre.md](fase-1-base-devops-sre.md) |
| 2 — Fundamentos de Backend | 5 a 8 | Python intermediário, HTTP/REST, PostgreSQL, FastAPI, SQLAlchemy | [fase-2-fundamentos-backend.md](fase-2-fundamentos-backend.md) |
| 3 — Backend profissional | 9 a 12 | Autenticação, testes, Redis/filas, observabilidade | [fase-3-backend-profissional.md](fase-3-backend-profissional.md) |
| 4 — Arquitetura, deploy e mercado | 13 a 16 | Arquitetura, Kubernetes/OpenShift, algoritmos, portfólio, candidatura | [fase-4-arquitetura-deploy-mercado.md](fase-4-arquitetura-deploy-mercado.md) |

Quer ver como isso se encaixa no roteiro de 6 meses de referência? Veja o [mapa 6 meses ↔ 16 semanas](mapa-6-meses.md).

## Ritmo

| Fase | Segunda a sexta | Sábado | Domingo | Total/semana |
|------|-----------------|--------|---------|--------------|
| 1 | 1 h | 1 h | livre | ~6 h |
| 2 a 4 | 1 h | 2 h (entrega da semana) | livre | ~7 h |

Regra de ouro: **1:1**. Cada hora consumindo conteúdo vale uma hora escrevendo código, sem tutorial aberto. Quando o tempo for curto, a versão compacta é 30 min de conteúdo + 30 min de código.

## Ritual semanal (todo sábado, nos últimos 30 min)

1. **Autoteste:** feche tudo, abra um arquivo vazio e reproduza o que aprendeu.
2. **Decisões:** registre em `anotacoes/semana-XX.md` e, quando for decisão de projeto, em um ADR ([modelo](../projetos/agendamento-api/adr/0000-template.md)).
3. **Mini-entrevista (a partir da Semana 9):** 15 min com o [prompt do entrevistador](../agente/prompts/entrevistador-backend.md). Pontos fracos vão para [flashcards/pontos-fracos.md](../flashcards/pontos-fracos.md).
4. **Progresso:** atualize [progresso.md](../progresso.md) e marque `[x]` na semana concluída.

## Se atrasar, corte nesta ordem

Atrasar faz parte. Não dobre as horas para compensar. Corte primeiro o que é conceito de "nice to have" e **nunca** corte o núcleo.

| Pode cortar ou adiar (nesta ordem) | Nunca cortar |
|-----------------------------------|--------------|
| 1. Kafka (só conceito), gRPC "hello world", saga | Git e GitHub |
| 2. Tracing com OpenTelemetry | SQL puro, modelagem, índices, transações |
| 3. Ansible roles (mantenha inventário + 1 playbook) | Autenticação e autorização entendidas |
| 4. Rate limiting, blue-green/canary (ficam só no conceito) | Testes das regras de negócio |
| 5. Algoritmos além do nível Easy | Docker + CI verde |
| | Projeto de agendamento + README + ADRs |
| | Mini-entrevistas e candidaturas |

## Atalhos

- Prática por conceito: [exercicios/](../exercicios/)
- Por baixo do framework: [fundamentos/](../fundamentos/)
- Materiais por semana: [recursos/por-semana.md](../recursos/por-semana.md)
- Seu professor de IA: [agente/](../agente/)
