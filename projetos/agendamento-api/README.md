# Sistema de agendamento (projeto principal)

## Problema que resolve

Clientes marcam horários com profissionais de um estabelecimento (clínica, salão, consultoria). O sistema precisa impedir conflitos, respeitar horários de funcionamento e aplicar políticas de cancelamento. **Não é um CRUD simples.**

## Documentos

| Documento | Para quê |
|-----------|----------|
| [regras-de-negocio.md](regras-de-negocio.md) | Regras (RN-xx), perfis e perguntas em aberto para você decidir |
| [cenarios-de-concorrencia.md](cenarios-de-concorrencia.md) | O problema do double booking e como investigá-lo |
| [adr/](adr/) | Decisões técnicas registradas, com o porquê |

## Evolução por semana

| Semana | O que o projeto ganha |
|--------|-----------------------|
| 7 | Modelagem das regras e estrutura inicial da API |
| 8 | Persistência em PostgreSQL + experimento de concorrência |
| 9 | Login, JWT e rotas protegidas por papel |
| 10 | Testes das regras (conflito, permissão, cancelamento, concorrência) |
| 11 | Cache de horários disponíveis e worker para confirmações (somente se houver problema real) |
| 12 | Observabilidade e SLO |
| 14 | Deploy no cluster de laboratório |
| 16 | README profissional com decisões e demo |

## Perguntas que o README final precisa responder

1. Que problema esse sistema resolve?
2. Quais são as regras de negócio?
3. Como rodar?
4. Qual a arquitetura?
5. Quais decisões importantes eu tomei (e por quê)?
6. Que desafios encontrei?
7. Como testar?
8. Onde está a documentação?
9. Quais as referências?
10. Onde está a demo online?

## Referências de inspiração

[Calendly](https://calendly.com/features), [Google Calendar API](https://developers.google.com/calendar/api/concepts) e o código aberto do [Cal.com](https://github.com/calcom/cal.com).
