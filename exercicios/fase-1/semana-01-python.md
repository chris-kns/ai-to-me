# Semana 1: exercícios de Python

> **Regra 1:1.** Cada bloco de conteúdo vale um bloco igual de código, sem tutorial aberto. Terminou o exercício? Feche tudo, abra um arquivo vazio e tente de novo (autoteste).
>
> Os exercícios são **encadeados**: usam um mesmo cenário (inventário de servidores) para os conceitos trabalharem juntos, como no código real.

## Dados de exemplo

Salve como `servidores.csv` (todos os nomes e IPs são fictícios):

```csv
nome,site,so,disco_pct,uptime_s,ip
srv-web-01,SITE-A,linux,45,864000,10.0.1.10
srv-web-02,SITE-A,linux,91,172800,10.0.1.11
srv-db-01,SITE-A,linux,78,2592000,10.0.1.20
srv-ad-01,SITE-B,windows,62,432000,10.0.2.5
srv-ad-02,SITE-B,windows,95,3600,10.0.2.6
srv-app-01,SITE-B,linux,30,1209600,10.0.1.10
```

Repare: `srv-app-01` tem um IP repetido. Isso **não é acidente**.

---

## Dia 1 (Seg): variáveis, tipos, condicionais e loops

**1. Variáveis e tipos**
- *Problema:* converta um uptime em segundos para o formato `Xd Yh Zm`.
- *Aceite:* `864000` vira `10d 0h 0m`. Use `//`, `%` ou `divmod`, e f-string.
- *Por quê?* Qual a diferença entre `/` e `//`? O que acontece com `int("10.5")`?

**2. Condicionais**
- *Problema:* classifique o uso de disco: abaixo de 70 é `OK`, de 70 a 89 é `ATENCAO`, 90 ou mais é `CRITICO`.
- *Aceite:* teste os limites 69, 70, 89 e 90.
- *Por quê?* Por que a ordem dos `if/elif` importa? Em qual valor erros de limite costumam aparecer?

**3. Loops**
- *Problema:* percorra os servidores e conte quantos estão `CRITICO`. Depois, com `while`, simule 3 tentativas de conexão que falham 2 vezes e funcionam na terceira.
- *Aceite:* o `while` precisa terminar sempre (sem loop infinito).
- *Por quê?* Quando `for` e quando `while`? O que `break` e `continue` mudam?

## Dia 2 (Ter): funções e escopo

**4. Funções**
- *Cenário:* extraia as lógicas dos exercícios 1 e 2 para `formatar_uptime(segundos)` e `classificar_disco(pct)`.
- *Aceite:* as funções **retornam** valores (não imprimem). Tenham docstring de uma linha.
- *Pegadinha:* escreva `registrar(servidor, historico=[])` e chame duas vezes. O que acontece? (Veja a pegadinha 1.)
- *Por quê?* Por que retornar é melhor do que imprimir dentro da função? Qual a diferença entre parâmetro e argumento?

## Dia 3 (Qua): listas, tuplas, sets e dicionários

**5. Listas**
- *Problema:* ordene os servidores por uso de disco (maior primeiro) e extraia os 3 piores. Depois, gere uma lista só com os nomes dos críticos usando comprehension.
- *Por quê?* `sorted()` ou `.sort()`? Qual altera a lista original?

**6. Dicionários**
- *Modelagem:* represente cada servidor como um dicionário. Depois, agrupe por site (`{"SITE-A": [...], "SITE-B": [...]}`) e conte servidores por sistema operacional.
- *Por quê?* Quando um dicionário é melhor do que uma lista? O que acontece se a chave não existir (`[]` vs `.get`)?

**7. Tuplas**
- *Problema:* crie `(nome, ip)` para cada servidor e use desempacotamento em um `for`. Faça uma função que devolve `(total, criticos)`.
- *Por quê?* Por que uma tupla pode ser chave de dicionário e uma lista não?

**8. Sets**
- *Problema:* o IP `10.0.1.10` aparece duas vezes. Detecte duplicados. Depois: dado o conjunto de hosts do inventário e o conjunto dos que estão no monitoramento, descubra quais **não estão monitorados**.
- *Por quê?* Qual a complexidade de `x in lista` vs `x in set`? Quando usar cada um?

## Dia 4 (Qui): exceções, módulos e arquivos

**9. Exceções**
- *Cenário:* leia o percentual de disco que o usuário digita. Trate `ValueError` (texto) e valores fora de 0 a 100 com uma exceção própria `DadoInvalidoError`.
- *Aceite:* o programa não quebra com entrada inválida e **diz o motivo**.
- *Por quê?* Por que `except:` puro é perigoso? Quando usar `finally`?

**10. Módulos**
- *Problema:* separe em `servidores.py` (funções de dados), `relatorio.py` (formatação) e `main.py` (entrada). Use `if __name__ == "__main__":`.
- *Pegadinha:* faça `servidores.py` importar `relatorio.py` e vice-versa. O que acontece? (import circular)
- *Por quê?* Por que separar? Como você decide em qual módulo cada função mora?

**11. Arquivos**
- *Problema:* leia o `servidores.csv` com `csv` e `pathlib`, e grave um relatório em texto **e** em JSON.
- *Aceite:* use `with`. Trate o arquivo inexistente com uma mensagem clara.
- *Por quê?* Por que `with open`? O que é *encoding* e por que importa?

## Dia 5 (Sex): venv, pacotes e orientação a objetos

**12. venv e pacotes**
- *Problema:* crie um `venv`, instale um pacote (`rich` ou `requests`), gere o `requirements.txt` e **recrie o ambiente do zero** em outra pasta.
- *Aceite:* o projeto roda no ambiente novo sem ajuste manual.
- *Por quê?* O que o `venv` isola? Por que `requirements.txt` vai para o Git e o `venv/` não?

**13. Orientação a objetos básica**
- *Problema:* crie a classe `Servidor` com atributos, o método `status()` (usa `classificar_disco`) e `__repr__`.
- *Por quê?* Quando uma classe vale mais do que um dicionário? O que o `self` representa?

---

## Sábado: mini projeto integrador

**Relatório de inventário de servidores (CLI)**

Escolha este ou um dos mini projetos do plano (conversor de moeda, gerenciador de tarefas, cadastro, leitor de arquivo, jogo no terminal). O projeto **não precisa impressionar, precisa fazer você pensar**.

Critérios de aceite do relatório:
- [ ] Lê `servidores.csv` e valida cada linha (disco entre 0 e 100, IP no formato válido).
- [ ] Mostra o uptime legível e a classificação de disco por servidor.
- [ ] Agrupa por site e mostra o total de críticos de cada um.
- [ ] Detecta IPs duplicados e os lista.
- [ ] Linhas inválidas **não derrubam** o programa: são reportadas ao final.
- [ ] Gera `relatorio.txt` e `relatorio.json`.
- [ ] Código separado em módulos, funções com docstring, dependências em `requirements.txt`.
- [ ] Commitado no GitHub com um `README.md` curto.

## Autoteste da semana

Em 10 min, de um **arquivo vazio**, sem consulta, escreva:

1. Uma função que recebe uma lista de dicionários e devolve um agrupamento por uma chave.
2. Um `try/except` que lê um arquivo e trata a ausência dele.
3. Uma comprehension que filtra e transforma.
4. Uma classe com `__init__`, um método e `__repr__`.

Se travou: você **reconheceu**, não aprendeu. Anote em [flashcards/pontos-fracos.md](../../flashcards/pontos-fracos.md) e revise amanhã.

## Perguntas para defender

- Por que organizei o código assim?
- Qual estrutura de dados escolhi em cada parte, e por quê?
- O que acontece se o CSV tiver uma linha quebrada?
- O que eu faria diferente numa segunda versão?
