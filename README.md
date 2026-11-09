# Plano de Estudos: DevOps/SRE + Backend Engineer

## Objetivo

Em cerca de **16 semanas (~4 meses)**, construir o perfil de quem **domina infraestrutura e também constrói, testa e opera uma aplicação backend de ponta a ponta** — um diferencial raro no mercado.

> O objetivo não é dominar Python em 16 semanas — isso não existe. O objetivo é **demonstrar competência suficiente para disputar uma vaga** e defender suas decisões numa entrevista.

## Filosofia e premissas

Estes mantras guiam todo o plano. Releia sempre que perder o foco:

1. **"Isso aumenta minha capacidade de construir e demonstrar competência? Se não, fica pra depois."**
2. **"Escrever código e botar a mão na massa tem que estar presente do dia 1 até o presente."**
3. **"Esse projeto é vivo — está sempre em constante evolução!"**
4. **"Software não é a recompensa da programação, é uma de diversas formas de aprender!"**

## Método de estudo

| Regra | O que significa |
|-------|-----------------|
| **1:1** | Cada hora consumindo conteúdo = 1 hora escrevendo código, **sem tutorial aberto** |
| **Autoteste** | Terminou um conceito → fecha tudo → abre arquivo vazio → consegue reproduzir? Se não, ainda não aprendeu |
| **Decisões explicáveis** | Toda escolha técnica precisa responder "por quê?" — se não sabe explicar, precisa estudar mais |
| **IA como professor** | Use para questionar, revisar raciocínio e simular entrevistas — não para copiar respostas |

## Projetos fio condutor

### 1. API de inventário de infraestrutura (foco DevOps/SRE)
Servidores, sites e serviços. Nasce como mini projeto na semana 1, ganha banco, autenticação, testes, cache e filas, e termina rodando num cluster Kubernetes com CI/CD e monitoramento.

### 2. Sistema de agendamento (foco Backend)
Projeto principal para demonstrar maturidade técnica em entrevistas. **Não é um CRUD simples** — possui regras de negócio reais:
- Usuário não pode agendar horário já ocupado
- Horários de funcionamento configuráveis
- Políticas de cancelamento
- Bloqueio de agenda do profissional
- Diferentes perfis: **cliente**, **profissional**, **admin**
- Concorrência: o que acontece quando dois clientes tentam o mesmo horário?

> Projetos competentes não são os que possuem mais tecnologias, mas sim os que demonstram mais **decisões** e **maturidade técnica**.

Ambos vão para o GitHub como portfólio.

## As 4 fases

| Fase | Período | Tema |
|------|---------|------|
| 1 — Base DevOps/SRE | Semanas 1 a 4 | Python, Git, CI/CD, Docker, Ansible, Prometheus/Grafana |
| 2 — Fundamentos de Backend | Semanas 5 a 8 | Python intermediário, HTTP/REST, PostgreSQL, FastAPI, SQLAlchemy |
| 3 — Backend profissional | Semanas 9 a 12 | Autenticação, testes, Redis/filas, observabilidade |
| 4 — Arquitetura, deploy e mercado | Semanas 13 a 16 | Arquitetura, Kubernetes/OpenShift, algoritmos, portfólio |

## Ritmo recomendado

- **Fase 1:** 1 h por dia
- **Fases 2 a 4:** 1 h de segunda a sexta (teoria e exercícios) + **2 h no sábado** (entrega da semana). Domingo livre.
- Total: ~7 h por semana. Se algum sábado falhar, não acumule — retome de onde parou.

## Competências-alvo

Ao final das 16 semanas, você deve ser capaz de:

1. **Entrar num sistema** e entender o que está acontecendo
2. **Identificar um problema** e avaliar soluções
3. **Construir uma solução** funcional, testada e monitorada
4. **Explicar suas decisões** com clareza e fundamento

## Navegação rápida

- [📅 Cronograma semanal](cronograma.md)
- [📚 Recursos e materiais](recursos.md)
- [📝 Anotações (template)](anotacoes/semana-01.md)

## Nota sobre linguagens

**Python não é uma profissão. Python é uma ferramenta.** Este plano usa Python para construir software backend — uma linguagem bem dominada vale mais que três superficiais. Node.js/TypeScript e Go podem ser estudados depois da semana 16 se necessário.
