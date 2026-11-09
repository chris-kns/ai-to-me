# Plano de Estudos: DevOps/SRE + Backend Engineer

## Objetivo

Em cerca de **16 semanas (~4 meses)**, construir o perfil de quem **domina infraestrutura e também constrói, testa e opera uma aplicação backend de ponta a ponta**, um diferencial raro no mercado.

> O objetivo não é dominar Python em 16 semanas, isso não existe. O objetivo é **demonstrar competência suficiente para disputar uma vaga** e defender suas decisões numa entrevista.

## Comece aqui

1. Leia este README até o fim (10 min).
2. Monte o seu professor de IA: [agente/](agente/README.md).
3. Abra a [Semana 1](plano/fase-1-base-devops-sre.md), faça os [exercícios](exercicios/fase-1/semana-01-python.md) e preencha [anotacoes/semana-01.md](anotacoes/semana-01.md).
4. Todo sábado, faça o [ritual semanal](plano/README.md#ritual-semanal-todo-sábado-nos-últimos-30-min) e atualize o [progresso](progresso.md).

## Filosofia e premissas

Estes mantras guiam todo o plano. Releia sempre que perder o foco:

1. **"Isso aumenta minha capacidade de construir e demonstrar competência? Se não, fica pra depois."**
2. **"Escrever código e botar a mão na massa tem que estar presente do dia 1 até o presente."**
3. **"Esse projeto é vivo, está sempre em constante evolução!"**
4. **"Software não é a recompensa da programação, é uma de diversas formas de aprender!"**

## Método de estudo

| Regra | O que significa |
|-------|-----------------|
| **1:1** | Cada hora consumindo conteúdo = 1 hora escrevendo código, **sem tutorial aberto** (ou 30 min + 30 min) |
| **Autoteste** | Terminou um conceito → fecha tudo → abre arquivo vazio → consegue reproduzir? Se não, ainda não aprendeu, só reconheceu |
| **Decisões explicáveis** | Toda escolha técnica precisa responder "por quê?". Se não sabe explicar, precisa estudar mais |
| **Pegadinhas** | Exercícios com armadilhas escondidas: o que importa é perceber quando algo sai do roteiro ([pegadinhas](fundamentos/pegadinhas-python.md)) |
| **IA como professor** | Use para questionar, revisar raciocínio e simular entrevistas, **não** para copiar respostas |
| **Tecnologia só com problema** | Redis, filas e afins só entram se resolverem um problema que o projeto **tem agora** |

## Projetos fio condutor

### 1. API de inventário de infraestrutura (foco DevOps/SRE)

Servidores, sites e serviços. Nasce na semana 1, ganha banco, autenticação, testes, cache e filas, e termina rodando num cluster Kubernetes com CI/CD e monitoramento. → [especificação](projetos/inventario-api/README.md)

### 2. Sistema de agendamento (foco Backend)

Projeto principal para demonstrar maturidade técnica em entrevistas. **Não é um CRUD simples**, tem regras de negócio reais:

- Usuário não pode agendar horário já ocupado
- Horários de funcionamento configuráveis
- Políticas de cancelamento
- Bloqueio de agenda do profissional
- Diferentes perfis: **cliente**, **profissional**, **admin**
- Concorrência: o que acontece quando dois clientes tentam o mesmo horário?

→ [regras de negócio](projetos/agendamento-api/regras-de-negocio.md) · [concorrência](projetos/agendamento-api/cenarios-de-concorrencia.md)

> Projetos competentes não são os que possuem mais tecnologias, mas sim os que demonstram mais **decisões** e **maturidade técnica**.

Ambos vão para o GitHub como portfólio, em repositórios próprios. Este repositório guarda o plano, as regras e as decisões.

## As 4 fases

| Fase | Período | Tema |
|------|---------|------|
| [1 — Base DevOps/SRE](plano/fase-1-base-devops-sre.md) | Semanas 1 a 4 | Python, Git, Docker, CI/CD, Ansible, Prometheus/Grafana, SLOs |
| [2 — Fundamentos de Backend](plano/fase-2-fundamentos-backend.md) | Semanas 5 a 8 | Python intermediário, HTTP/REST, PostgreSQL, FastAPI, SQLAlchemy |
| [3 — Backend profissional](plano/fase-3-backend-profissional.md) | Semanas 9 a 12 | Autenticação, testes, Redis/filas, observabilidade |
| [4 — Arquitetura, deploy e mercado](plano/fase-4-arquitetura-deploy-mercado.md) | Semanas 13 a 16 | Arquitetura, Kubernetes/OpenShift, algoritmos, portfólio, candidatura |

Como isso se relaciona com o roteiro de 6 meses: [mapa 6 meses ↔ 16 semanas](plano/mapa-6-meses.md).

## Ritmo recomendado

- **Fase 1:** 1 h por dia, de segunda a sábado (~6 h por semana).
- **Fases 2 a 4:** 1 h de segunda a sexta (teoria e exercícios) + **2 h no sábado** (entrega da semana). Domingo livre (~7 h por semana).
- Se algum sábado falhar, **não acumule**: retome de onde parou. Se atrasar, veja [o que cortar e o que nunca cortar](plano/README.md#se-atrasar-corte-nesta-ordem).

## Competências-alvo

Ao final das 16 semanas, você deve ser capaz de:

1. **Entrar num sistema** e entender o que está acontecendo
2. **Identificar um problema** e avaliar soluções
3. **Construir uma solução** funcional, testada e monitorada
4. **Explicar suas decisões** com clareza e fundamento

## Estrutura do repositório

```text
.
├── README.md                    # você está aqui
├── progresso.md                 # marcos e números semanais
├── CHANGELOG.md                 # histórico da reestruturação
├── plano/                       # o plano, por fase, e o mapa de 6 meses
├── recursos/                    # materiais por semana e pós-plano
├── exercicios/                  # um problema ou cenário por conceito
├── fundamentos/                 # o que existe por baixo do framework, pegadinhas
├── projetos/                    # especificação dos 2 projetos, regras e ADRs
├── anotacoes/                   # uma página por semana (+ modelo)
├── flashcards/                  # pontos fracos, método e banco de perguntas
├── mercado/                     # análise de vagas e candidaturas
├── agente/                      # prompt do professor de IA e prompts de apoio
└── docs/origem/                 # materiais que deram origem ao plano
```

## Nota sobre linguagens

**Python não é uma profissão. Python é uma ferramenta.** Este plano usa Python para construir software backend: uma linguagem bem dominada vale mais que três superficiais. O que fica para depois (Terraform, cloud, CKA, Go, Node/TypeScript) está em [recursos/pos-plano.md](recursos/pos-plano.md).
