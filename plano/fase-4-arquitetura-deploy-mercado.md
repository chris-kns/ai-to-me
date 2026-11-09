# Fase 4 — Arquitetura, Deploy e Mercado (Semanas 13 a 16)

> ← [Voltar ao plano](README.md) · Marque `[x]` ao concluir cada semana.

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
| Seg | Imagem enxuta e sem root (no OpenShift o container roda com UID arbitrário) |
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
> Se travar, anote o ponto fraco. Use [flashcards](../flashcards/README.md) para revisar: é conceito que falta ou prática de código?

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

> 🔄 **Não espere terminar para se candidatar.** Candidatura é um loop: ajusta currículo → entrevista → recebe feedback → estuda → aplica novamente. Registre tudo em [mercado/candidaturas.md](../mercado/candidaturas.md).

**Entrega:** portfólio completo, currículo pronto e candidaturas em andamento.
