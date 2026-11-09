# Mapa: roadmap de 6 meses ↔ plano de 16 semanas

O roteiro de referência (a imagem e o prompt originais) divide a jornada em 6 meses focados em **Python backend**. Este plano tem 16 semanas e adiciona uma base **DevOps/SRE** (Fase 1), porque é o seu diferencial de partida. A tabela abaixo mostra onde cada tema do roteiro original vive no plano.

## O roteiro original

| Mês | Temas |
|-----|-------|
| 1 | Python de verdade · fundamentos · problemas pequenos · muito código |
| 2 | engenharia básica · Git · testes · organização · debugging |
| 3 | back-end · HTTP · frameworks · projeto principal |
| 4 | PostgreSQL · SQL · autenticação · regras de negócio |
| 5 | Docker · testes melhores · deploy · logs · produção · entrevista |
| 6 | polir · projeto · GitHub · currículo · entrevista · candidatura |

## Onde cada mês aparece nas 16 semanas

| Mês original | Semanas do plano | Observação |
|--------------|------------------|------------|
| 1 — Fundamentos | 1 | Python vira 1 semana intensa, com exercícios por conceito |
| 2 — Engenharia básica | 2, 3 (parcial), 5 (parcial) | Git, organização, debugging, tipagem, logs, pre-commit/ruff |
| 3 — Back-end e projeto | 5, 7 | HTTP/REST, FastAPI e início do projeto de agendamento |
| 4 — SQL, auth, regras | 6, 8, 9 | SQL puro antes do ORM, concorrência, JWT/RBAC |
| 5 — Docker, produção | 3, 10 a 12, 14 | Docker e CI entram cedo (Fase 1), produção na Fase 3/4 |
| 6 — Portfólio e candidatura | 15, 16 | README, ADRs, currículo, vagas, candidaturas |
| *(extra, sem equivalente)* | 4, 13 | Ansible, Prometheus/Grafana, SLOs, arquitetura e K8s |

## O que muda em relação ao roteiro de 6 meses

- **Mais curto e mais denso.** São ~112 h no total (16 × 7 h). O roteiro original se estende por 6 meses; aqui o ritmo é maior.
- **Entrevista começa antes.** No original ela aparece no mês 5. Aqui as mini-entrevistas semanais começam na Semana 9.
- **Mercado desde cedo.** A análise de vagas reais (Semana 5) decide framework, banco e cloud com dados, como o roteiro pede no mês 3.
- **Docker e CI na Fase 1.** O original deixa para o mês 5. Para quem vem de infraestrutura, adiantar faz sentido e destrava o projeto desde o início.

## Quer o ritmo de 6 meses?

Se 7 h por semana não couber, estique em vez de cortar conteúdo: **uma semana do plano = ~1,6 semana de calendário** (≈ 4,3 h por semana, cerca de 26 semanas no total). Mantenha a ordem, o sábado como dia de entrega e o ritual semanal. O que não pode mudar é a regra 1:1.
