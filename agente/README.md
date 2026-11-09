# Agente de estudo

Esta pasta transforma uma IA (ex.: um Projeto do Claude) no seu professor, revisor e entrevistador.

## Montando o agente

1. Crie um **Projeto** no Claude.
2. Cole o conteúdo de [`prompt-professor.md`](prompt-professor.md) (abaixo da linha) nas instruções do projeto.
3. Anexe ao projeto: `README.md`, `plano/`, `anotacoes/`, `projetos/` e `flashcards/`.
4. Abra uma conversa e escreva: `/semana 1`.

## Prompts de apoio

Use quando quiser uma conversa focada, em vez do agente completo.

| Prompt | Quando usar |
|--------|-------------|
| [entrevistador-backend](prompts/entrevistador-backend.md) | Mini-entrevista de sábado e simulações |
| [revisor-de-codigo](prompts/revisor-de-codigo.md) | Antes de abrir/mergear um PR |
| [gerador-de-exercicios](prompts/gerador-de-exercicios.md) | Depois de estudar um conceito |
| [gerador-de-flashcards](prompts/gerador-de-flashcards.md) | Transformar pontos fracos em revisão |
| [retrospectiva-semanal](prompts/retrospectiva-semanal.md) | Fechamento do sábado |

## Rotina sugerida

| Quando | O que fazer com o agente |
|--------|--------------------------|
| Início da semana | `/semana <n>` para alinhar o que entregar |
| Durante o estudo | `/conceito`, `/exercicio`, `/pegadinha` |
| Antes do commit/PR | `/revisar` |
| Sábado, final | `/entrevista` (a partir da Semana 9) e `/retro` |
| Quando travar | Registrar o ponto fraco e pedir `/flashcards` |

## Regra de ouro

Se a IA me der a resposta pronta antes de eu tentar, **eu perdi a aula**. Peça uma pista, não a solução.

A origem deste prompt está em [docs/origem/prompt-original.md](../docs/origem/prompt-original.md).
