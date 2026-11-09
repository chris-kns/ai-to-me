# Projetos

São dois projetos fio condutor. O **código** de cada um vive em um **repositório próprio** (ex.: `inventario-api`, `agendamento-api`). Aqui ficam o que não é código: especificação, regras de negócio, decisões (ADRs) e o plano de evolução.

| Projeto | Foco | Papel no plano |
|---------|------|----------------|
| [inventario-api](inventario-api/README.md) | DevOps/SRE | Nasce na semana 1 e é a base para praticar Docker, CI, monitoramento e deploy |
| [agendamento-api](agendamento-api/README.md) | Backend | Projeto principal: regras de negócio reais, concorrência, autenticação e portfólio |

> Projetos competentes não são os que têm mais tecnologias, e sim os que demonstram mais **decisões** e **maturidade técnica**.

## Como se relacionam

Os dois usam a mesma stack (FastAPI, PostgreSQL, Docker, CI, Prometheus). O inventário é onde você erra barato e aprende a operar. O agendamento é onde você pratica regras de negócio e prova maturidade em entrevista.
