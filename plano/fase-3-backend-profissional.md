# Fase 3 — Backend Profissional (Semanas 9 a 12)

> ← [Voltar ao plano](README.md) · Marque `[x]` ao concluir cada semana.

**Ritmo:** 1 h seg–sex + 2 h sábado

> 🎤 **Ritual novo (a partir da Semana 9):** no fim de todo sábado, 15 min de mini-entrevista sobre as decisões da semana ([prompt do entrevistador](../agente/prompts/entrevistador-backend.md)). Pontos fracos vão para [flashcards/pontos-fracos.md](../flashcards/pontos-fracos.md).

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
| **Sáb** | **Cobertura ≥ 70%, teste de concorrência e pipeline verde** |

> 💡 Testes existem para **validar comportamentos que não podem quebrar**. Teste as regras de negócio do agendamento: conflito de horário, permissões, cancelamento. Inclua um teste de concorrência (2 threads no mesmo horário) e a diferença entre `401` e `403`.

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
