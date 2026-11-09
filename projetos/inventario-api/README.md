# API de inventário de infraestrutura

## Problema que resolve

Equipes de infraestrutura costumam manter o inventário (servidores, sites, serviços) em planilhas. Uma API permite consultar, atualizar e **automatizar**: o Ansible lê o inventário, o monitoramento sabe o que deve existir e relatórios saem sem copiar e colar.

## Entidades iniciais (ponto de partida)

| Entidade | Ideia |
|----------|-------|
| Site | Local físico ou lógico onde há servidores |
| Servidor | Máquina física ou virtual, com SO, IP e função |
| Serviço | O que roda em um servidor (nome, porta, criticidade) |

Questione: um servidor pode estar em mais de um site? Um serviço roda em vários servidores? O que significa "desativado" (apagar ou marcar)?

## Evolução por semana

| Semana | O que o projeto ganha |
|--------|-----------------------|
| 4 | Repositório base com estrutura, README, CI e monitoramento rodando |
| 5 | Contrato da API (endpoints, entradas e saídas) |
| 7 | CRUD em memória com validação (Pydantic) |
| 8 | PostgreSQL, SQLAlchemy, migrations, `docker compose` |
| 9 | Autenticação JWT e RBAC |
| 10 | Testes com cobertura ≥ 70% |
| 11 | Cache com Redis (se houver um problema real) |
| 12 | Logs estruturados, `/health`, `/metrics`, dashboard e SLO |
| 14 | Deploy no cluster de laboratório |

## Desafio de integração (DevOps/SRE)

Faça um playbook Ansible que consome o endpoint de servidores da API como **inventário dinâmico**. É o ponto em que as duas trilhas se encontram.

## Critério de pronto

- [ ] `docker compose up` sobe a API e o banco do zero
- [ ] Pipeline de CI verde (lint, testes, build da imagem)
- [ ] Dashboard com taxa, erros e duração (RED) e 1 alerta
- [ ] README com problema, como rodar, arquitetura e decisões
- [ ] Pelo menos 3 ADRs registrados
