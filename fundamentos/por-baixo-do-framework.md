# O que existe por baixo do framework

> Saber FastAPI é bom. **Saber o que o FastAPI faz por você é o que te contrata.** Quem só repete tutorial trava quando sai do roteiro. Esta tabela é o seu mapa: para cada recurso do framework, o que existe por baixo e uma pergunta de teste.

| Recurso do framework | O que existe por baixo | Pergunta de teste |
|----------------------|------------------------|-------------------|
| **Rota** (`@app.get("/servidores")`) | Uma tabela que liga *método HTTP + caminho* a uma função. O servidor recebe bytes, interpreta a request line, os headers e o body | O que chega ao seu código quando alguém faz `curl -v`? Em qual ponto a rota é escolhida? |
| **Validação** (Pydantic) | Conversão e checagem de tipos na entrada; serialização para JSON na saída | Por que um campo inválido vira `422` e não `400`? O que é serializar? |
| **Injeção de dependência** (`Depends`) | Funções executadas a cada request, cujo resultado é entregue ao handler | Qual é o ciclo de vida da sessão de banco? Quem fecha a conexão? |
| **Middleware** | Uma cadeia entre o servidor e a rota, que pode ler/alterar request e response | Onde entram CORS, logs e `correlation id`? Qual a ordem de execução? |
| **ORM** (SQLAlchemy) | SQL gerado, uma *session* que agrupa mudanças (unit of work), transações e pool de conexões | Qual SQL esta linha gera? O que é o problema N+1? O que acontece no `commit` e no `rollback`? |
| **Migrations** (Alembic) | Histórico versionado do schema, aplicado em ordem | Como o schema de produção fica igual ao de desenvolvimento? E se uma migration falha no meio? |
| **Sessão e login** | Cookie de sessão (estado no servidor) **ou** token assinado (estado no cliente, sem consulta ao servidor) | Onde fica o estado do usuário em cada abordagem? Como invalidar um JWT antes de expirar? |
| **Autorização** (RBAC) | Checagem, em cada endpoint, de *quem* é o usuário e *o que* ele pode fazer | Qual a diferença entre `401` e `403`? O que impede um cliente de ver agenda de outro? |
| **Template** (Jinja2) | Renderização de texto no servidor, com *escaping* para evitar XSS | O que acontece se eu imprimir um campo do usuário sem escapar? |
| **Servidor** (uvicorn/gunicorn) | Processo(s) com event loop (ASGI) ou workers (WSGI) | Quantos requests simultâneos uma `async def` aguenta? O que bloqueia o event loop? |
| **Proxy reverso e TLS** (nginx, Route) | Terminação de TLS, balanceamento, headers `X-Forwarded-*` | Onde o HTTPS termina? Como a API descobre o IP real do cliente? |
| **Configuração** (`.env`) | Variáveis de ambiente lidas no início do processo | Por que segredo não vai no Git? O que muda entre dev e prod sem tocar no código? |
| **Logs** | Linhas em `stdout`, coletadas pela plataforma | Por que logs estruturados (JSON)? O que é um `correlation id`? |

## Experimentos (10 minutos cada)

Faça com a API do projeto ou com um "hello world".

1. **Veja a request crua:** `curl -v http://localhost:8000/health`. Identifique método, caminho, headers e status.
2. **Quebre a validação de propósito:** envie um body inválido e leia o `422`. Descubra que campo o Pydantic reclamou.
3. **Veja o SQL:** ligue `echo=True` no engine do SQLAlchemy e dispare um endpoint. Conte as queries (existe N+1?).
4. **Trace a sessão:** coloque um `print` na dependência que abre a sessão e veja quando abre e quando fecha.
5. **Decodifique um JWT** sem a chave (jwt.io): o que está legível? Por que isso é aceitável?
6. **Bloqueie o event loop:** coloque `time.sleep(5)` num endpoint `async def` e chame 2 vezes em paralelo. Depois troque por `await asyncio.sleep(5)`.

## Como saber que aprendi

Consigo desenhar, em um papel, o caminho de um request: **cliente → DNS → TLS → proxy → servidor → middleware → rota → dependências → banco → resposta**, e dizer o que pode falhar em cada seta.
