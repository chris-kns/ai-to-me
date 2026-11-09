# Pegadinhas de Python

> Armadilhas que fazem o código "funcionar" até o dia em que não funciona. Use de duas formas: (1) tente **prever a saída antes de rodar**; (2) peça `/pegadinha` ao agente para plantar uma delas em um exercício.

Para cada item: preveja, rode, explique o *porquê* e só depois leia a explicação.

## 1. Argumento padrão mutável

```python
def adicionar(item, sacola=[]):
    sacola.append(item)
    return sacola

adicionar(1)
adicionar(2)   # o que retorna?
```

**Resultado:** `[1, 2]`. O valor padrão é criado **uma vez**, na definição da função, e reaproveitado. **Correção:** `sacola=None` e `if sacola is None: sacola = []`.

## 2. Cópia que não é cópia

```python
grade = [[0] * 3] * 3
grade[0][0] = 1
print(grade)
```

**Resultado:** `[[1, 0, 0], [1, 0, 0], [1, 0, 0]]`. As três linhas são **o mesmo objeto**. **Correção:** `[[0] * 3 for _ in range(3)]`.

## 3. Closure em loop

```python
funcoes = [lambda: i for i in range(3)]
print([f() for f in funcoes])
```

**Resultado:** `[2, 2, 2]`. A variável `i` é lida **quando a função é chamada**, não quando é criada. **Correção:** `lambda i=i: i`.

## 4. Dinheiro e ponto flutuante

```python
print(0.1 + 0.2 == 0.3)
```

**Resultado:** `False`. Floats são binários e aproximados. Para dinheiro (olá, conversor de moeda), use `decimal.Decimal` ou inteiros em centavos. Para comparar floats, `math.isclose`.

## 5. Alterar a lista enquanto percorre

```python
numeros = [2, 4, 6, 8]
for n in numeros:
    if n % 2 == 0:
        numeros.remove(n)
print(numeros)
```

**Resultado:** `[4, 8]`. Ao remover, os índices se deslocam e o loop pula elementos. **Correção:** percorra uma cópia ou construa uma nova lista com comprehension.

## 6. `+=` altera, `+` cria

```python
def f(xs):
    xs += [1]

a = [0]
f(a)
print(a)
```

**Resultado:** `[0, 1]`. Em listas, `+=` modifica **o objeto original**, que é de quem chamou a função. Com `xs = xs + [1]` isso não aconteceria.

## 7. Valor falsy confundido com "ausente"

```python
desconto = pedido.get("desconto") or 10
```

Se o desconto for `0`, vira `10`. `0`, `""`, `[]` e `None` são falsy. **Correção:** `if valor is None`.

## 8. Tupla de um elemento

```python
a = (1)
b = (1,)
print(type(a), type(b))
```

**Resultado:** `int` e `tuple`. Quem faz a tupla é a **vírgula**, não o parêntese.

## 9. `except:` que engole tudo

```python
try:
    processar()
except:
    pass
```

Esconde erros reais e captura até `KeyboardInterrupt` (Ctrl+C). **Correção:** capture a exceção específica (`except ValueError`) e registre no log. Se precisar de uma rede ampla, `except Exception`.

## 10. Data sem fuso horário (muito relevante para agendamento)

```python
from datetime import datetime, timezone

agora_ingenua = datetime.now()               # naive (sem fuso)
agora_consciente = datetime.now(timezone.utc)  # aware (com fuso)
```

Comparar com `<`, `>` ou subtrair um *naive* e um *aware* levanta `TypeError`. Guarde sempre em UTC e converta para o fuso do usuário/estabelecimento só na exibição (`zoneinfo`).

## 11. Sombreando funções nativas

```python
list = [1, 2, 3]
list("abc")   # TypeError: 'list' object is not callable
```

Nomes como `list`, `dict`, `id`, `type`, `input` são funções nativas. Se você reatribuir, as perde naquele escopo.

## 12. `dict[chave]` vs `dict.get(chave)`

`dict["x"]` levanta `KeyError`, o que é barulhento e seguro. `dict.get("x")` devolve `None`, o que é silencioso e perigoso se você usar o resultado depois. Escolha conscientemente.

## Meta-pegadinha

Se você acertou todas de primeira, peça ao agente pegadinhas de **Git, SQL e HTTP**. Elas existem, e são as que aparecem em produção.
