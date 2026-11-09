# Regras de negócio

> Este é um **rascunho para ser questionado**, não um contrato fechado. Para cada regra, decida, registre o motivo e transforme em teste. Um bom projeto tem regras que **alguém discordaria**.

## Regras iniciais

| ID | Regra | Status |
|----|-------|--------|
| RN-01 | Um profissional não pode ter dois agendamentos sobrepostos | decidida |
| RN-02 | Só se agenda dentro do horário de funcionamento (configurável) | decidida |
| RN-03 | Há política de cancelamento (prazo e consequência) | **a decidir** |
| RN-04 | O profissional pode bloquear a própria agenda (folga, almoço, férias) | decidida |
| RN-05 | Existem três perfis: cliente, profissional e admin | decidida |

## Perguntas em aberto (a decidir e justificar)

| Tema | Pergunta | Decisão | Por quê |
|------|----------|---------|---------|
| Duração | Cada serviço tem duração fixa? Como ela entra no cálculo de conflito? |  |  |
| Intervalo | Existe tempo de descanso entre atendimentos? |  |  |
| Antecedência | Antecedência mínima e máxima para agendar? |  |  |
| Cancelamento | Até quantas horas antes? Cancelar tarde tem multa ou apenas registro? |  |  |
| Reagendamento | É um cancelamento + novo agendamento, ou uma operação própria? |  |  |
| *No-show* | O que acontece quando o cliente não aparece? |  |  |
| Fuso | Em qual fuso o horário é armazenado e exibido? |  |  |
| Feriados | Como tratar dias sem atendimento? |  |  |
| Capacidade | Um profissional atende uma pessoa por vez? E serviços em grupo? |  |  |
| Retry | O cliente clica 2 vezes em "confirmar". Como evitar 2 agendamentos? |  |  |
| Lista de espera | Se o horário estiver ocupado, vale fila de espera? |  |  |
| Notificações | O que é enviado, quando, e o envio pode falhar sem derrubar o agendamento? |  |  |

## Perfis e permissões (proposta inicial: questione)

| Ação | Cliente | Profissional | Admin |
|------|---------|--------------|-------|
| Ver horários disponíveis | sim | sim | sim |
| Criar agendamento para si | sim | não | sim (em nome de alguém) |
| Cancelar o próprio agendamento | sim (respeitando RN-03) | n/a | sim |
| Ver a agenda de outro cliente | **não** | só dos seus atendimentos | sim |
| Bloquear a própria agenda | não | sim | sim |
| Configurar serviços e horários de funcionamento | não | não | sim |

Perguntas: quem pode cancelar o atendimento de um cliente? O admin vê dados pessoais? O que a API devolve quando um cliente pede a agenda de outro, `403` ou `404`? Por quê?

## Das regras aos testes

Cada regra decidida deve virar pelo menos um teste (Semana 10). Escreva o teste a partir da regra, **não** do código.

| Regra | Teste de exemplo |
|-------|------------------|
| RN-01 | Dois agendamentos sobrepostos no mesmo profissional: o segundo é rejeitado |
| RN-02 | Agendar às 03:00 é rejeitado |
| RN-04 | Horário bloqueado não aparece como disponível |
| RN-05 | Cliente não consegue acessar a agenda de outro cliente |
| concorrência | Duas requisições simultâneas ao mesmo horário: só uma é aceita |
