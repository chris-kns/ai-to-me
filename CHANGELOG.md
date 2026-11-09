# Changelog

## Reestruturação do repositório

Reorganização do plano em pastas, incorporação do prompt original de estudo (roadmap de 6 meses focado em Python backend) e consolidação do plano expandido DevOps/SRE + Backend.

### Adicionado

- **`agente/`**: prompt otimizado do professor (modos aprendizado e produtividade, protocolo por conceito, modo entrevista, atalhos) e 5 prompts de apoio (entrevistador, revisor de código, exercícios, flashcards, retrospectiva).
- **`exercicios/`**: 13 exercícios encadeados da Semana 1 (um por conceito) + mini projeto integrador com critérios de aceite.
- **`fundamentos/`**: mapa "o que existe por baixo do framework" (13 recursos, perguntas de teste, 6 experimentos) e 12 pegadinhas de Python.
- **`flashcards/`**: método (tipos C/P/D + caixas de Leitner), tabela de pontos fracos e banco com ~40 perguntas de entrevista com resposta-base.
- **`mercado/`**: guia de leitura de vagas, planilha de análise (decidir framework/banco/cloud com dados) e acompanhamento do loop de candidaturas.
- **`projetos/`**: especificação dos dois projetos, regras de negócio com perguntas em aberto, cenários de concorrência (double booking) e modelo de ADR.
- **`anotacoes/`**: uma página para cada uma das 16 semanas, geradas a partir do modelo, com seção de mini-entrevista a partir da Semana 9.
- **`plano/mapa-6-meses.md`**: correspondência entre o roteiro original de 6 meses e as 16 semanas.
- **`progresso.md`**, **`.gitignore`**, **`.gitattributes`**.

### Alterado

- `cronograma.md` dividido em `plano/fase-1..4` com índice, ritual semanal e "o que cortar se atrasar".
- `recursos.md` movido para `recursos/por-semana.md`; pós-plano em arquivo próprio.
- Plano expandido original movido para `docs/origem/`.
- **Fase 1:** ritmo explícito (seg a sáb), itens extras de Python (f-strings, comprehensions, `pathlib`, `json`, `datetime`...), prioridade definida para a semana 4.
- **Fase 2:** tarefa de mercado na semana 5; a quarta-feira da semana 5 deixou de repetir `pyproject`/`ruff`/`logging` (já vistos nas semanas 2 e 3) e passou a tratar de estrutura em camadas e configuração; fuso horário nas regras do agendamento; experimento de concorrência na semana 8.
- **Fase 3:** mini-entrevista semanal a partir da semana 9; teste de concorrência e `401` vs `403` na semana 10.
- **Fase 4:** nota sobre UID arbitrário no OpenShift; links para flashcards e candidaturas.

### Corrigido

- `recursos.md` tinha as semanas 2 a 4 da Fase 1 em ordem diferente do cronograma (Docker/CI estavam na semana 2 e Ansible na 3, mas o cronograma os coloca nas semanas 3 e 4). Realinhado.
- A Fase 1 dizia "1 h por dia" mas listava atividades de segunda a sábado. O ritmo agora está explícito.

### Observações

- A transcrição do vídeo de referência que acompanhava o prompt **não foi incluída** (conteúdo de terceiros). O arquivo `docs/origem/prompt-original.md` guarda apenas as instruções do autor.
- O primeiro commit desta sequência (`chore: snapshot...`) registra as alterações locais que já estavam pendentes no working tree antes da reestruturação.
- Dados de mercado propositalmente **não** foram incluídos: envelhecem rápido. Use `mercado/analise-de-vagas.md` para coletar os seus.
