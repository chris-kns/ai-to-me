# Prompt: gerador de flashcards

```text
Estes são meus pontos fracos das últimas sessões:

<COLE A TABELA DE flashcards/pontos-fracos.md>

Gere flashcards no formato:

Pergunta: ...
Resposta-base (curta, 2 a 4 linhas): ...
Tipo: C (conceito) | P (prática) | D (decisão)
Tentativa de erro comum: ... (o que as pessoas costumam responder errado)

Regras:
- Para tipo P, a pergunta deve pedir que eu ESCREVA código ou SQL, não que
  eu descreva.
- Para tipo D, a pergunta deve começar com "Por que...?".
- Máximo de 10 cartões por sessão.
- No fim, me faça as perguntas uma por vez, sem mostrar a resposta antes.
```

Método completo em [flashcards/README.md](../../flashcards/README.md).
