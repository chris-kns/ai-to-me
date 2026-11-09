# Banco de perguntas

Perguntas de entrevista com **resposta-base** (curta, para você conferir depois de tentar). Tente responder em voz alta **antes** de ler. Se a sua resposta foi mais fraca, registre em [pontos-fracos.md](pontos-fracos.md).

Tipos: **C** conceito · **P** prática · **D** decisão.

## HTTP e REST

| Pergunta | Resposta-base | Tipo |
|----------|---------------|------|
| `PUT` vs `PATCH`? | `PUT` substitui o recurso inteiro (e é idempotente). `PATCH` altera parcialmente. | C |
| O que é idempotência? | Repetir a mesma requisição leva ao mesmo estado final. `GET`, `PUT` e `DELETE` são idempotentes; `POST` normalmente não. | C |
| `401` vs `403`? | `401`: não autenticado (credencial ausente ou inválida). `403`: autenticado, mas sem permissão. | C |
| `400` vs `422`? | `400`: requisição malformada. `422`: bem formada, mas semanticamente inválida (é o que o FastAPI devolve em falha de validação). | C |
| O que significa *stateless* em REST? | Cada requisição carrega tudo que o servidor precisa. O servidor não guarda sessão entre requisições, o que facilita escalar horizontalmente. | C |
| O que é CORS e o que ele protege? | Política do **navegador** que bloqueia requisições entre origens diferentes, a menos que o servidor autorize por headers. Não substitui autenticação nem protege a API de outros clientes. | C |

## SQL e PostgreSQL

| Pergunta | Resposta-base | Tipo |
|----------|---------------|------|
| O que é um índice e qual o custo? | Estrutura (geralmente B-tree) que acelera busca e ordenação. Custa espaço e deixa escritas mais lentas. | C |
| Quando um índice **não** ajuda? | Tabela pequena, coluna de baixa seletividade, ou função aplicada na coluna sem índice funcional. | D |
| O que o `EXPLAIN ANALYZE` mostra? | O plano escolhido **e** o tempo real de execução (executa a query). Compare *Seq Scan* e *Index Scan*. | C |
| O que é ACID? | Atomicidade (tudo ou nada), Consistência (respeita as regras), Isolamento (transações não se atrapalham), Durabilidade (commit persiste). | C |
| `INNER JOIN` vs `LEFT JOIN`? | `INNER` só devolve linhas com correspondência nos dois lados. `LEFT` mantém todas da esquerda, com `NULL` onde não há correspondência. | P |
| `WHERE` vs `HAVING`? | `WHERE` filtra linhas antes de agrupar. `HAVING` filtra grupos depois das agregações. | P |
| `DELETE` vs `TRUNCATE`? | `DELETE` remove linhas (aceita `WHERE`, dispara triggers por linha). `TRUNCATE` esvazia a tabela inteira, mais rápido. | C |
| O que é o problema N+1? | 1 consulta para listar + N consultas para buscar relacionados. Resolve-se com `JOIN` ou *eager loading*. | C |
| Chave primária vs estrangeira? | Primária identifica a linha de forma única. Estrangeira garante que o valor exista na tabela referenciada. | C |

## Concorrência

| Pergunta | Resposta-base | Tipo |
|----------|---------------|------|
| O que é uma *race condition*? | Resultado que depende da ordem de operações concorrentes. Típico: *check-then-act* (checa se está livre, depois insere). | C |
| Como evitar dois agendamentos no mesmo horário? | A garantia precisa estar no **banco**: constraint (exclusão ou unicidade) ou lock dentro de uma transação. Validar só no código falha sob concorrência. | D |
| Lock otimista vs pessimista? | Pessimista trava antes de alterar. Otimista assume conflito raro e detecta ao gravar (coluna de versão), com *retry*. | C |
| Por que `SELECT ... FOR UPDATE` pode não bastar? | Só trava linhas **que existem**. Um `INSERT` novo na mesma janela passa. Trave uma linha "mestre" (o profissional) ou use isolamento `SERIALIZABLE` com retry. | D |

## Autenticação e segurança

| Pergunta | Resposta-base | Tipo |
|----------|---------------|------|
| Autenticação vs autorização? | Autenticação: *quem é você?* Autorização: *o que você pode fazer?* | C |
| O que tem dentro de um JWT? | Header (algoritmo), payload (claims como `sub` e `exp`) e assinatura. O payload é só codificado (Base64URL), **não criptografado**. A assinatura garante integridade. | C |
| Por que o token expira? | Limita o estrago de um roubo. Como o JWT é stateless, é difícil revogar antes do fim, por isso expira cedo e se renova com *refresh token*. | D |
| Como guardar senhas? | Nunca em texto puro nem com hash rápido (MD5/SHA). Use hash lento e com *salt*: argon2 ou bcrypt. | D |
| O que é SQL Injection e como prevenir? | Entrada do usuário interpretada como SQL. Previne-se com consultas parametrizadas (ou ORM) e validação de entrada. | C |
| OAuth2 vs OIDC? | OAuth2 delega **autorização** (acesso a recursos). OIDC é a camada de **identidade** sobre o OAuth2 (id token). | C |

## Docker, CI/CD e Kubernetes

| Pergunta | Resposta-base | Tipo |
|----------|---------------|------|
| Imagem vs container? | Imagem: template imutável em camadas. Container: instância em execução, com uma camada gravável. | C |
| Para que serve *multi-stage build*? | Compila/instala em um estágio e copia só o necessário para a imagem final: menor e com menos superfície de ataque. | D |
| CI vs Continuous Delivery vs Continuous Deployment? | CI integra e testa a cada mudança. Delivery deixa o artefato pronto para publicar (com aprovação). Deployment publica automaticamente. | C |
| Por que rodar container sem root? | Reduz o impacto de uma invasão. No OpenShift o container roda com UID arbitrário, então a imagem precisa funcionar assim. | D |
| *Liveness* vs *readiness*? | Liveness: se falhar, reinicia o pod. Readiness: se falhar, tira o pod do balanceamento sem reiniciar. | C |

## Observabilidade e SRE

| Pergunta | Resposta-base | Tipo |
|----------|---------------|------|
| Logs, métricas e traces? | Logs: eventos detalhados. Métricas: números agregados no tempo. Traces: caminho de uma requisição entre serviços. | C |
| SLI, SLO, SLA e *error budget*? | SLI: o que se mede. SLO: meta interna. SLA: contrato com consequência. *Error budget*: 100% − SLO, o quanto pode falhar. | C |
| Método RED vs USE? | RED (serviços): *Rate, Errors, Duration*. USE (recursos): *Utilization, Saturation, Errors*. | C |
| Como investigar uma API lenta? | Confirme com métricas (latência por rota), olhe traces/logs, verifique banco (`EXPLAIN`), depois recursos (CPU/memória) e dependências externas. Mude **uma coisa por vez**. | D |

## Arquitetura e Python

| Pergunta | Resposta-base | Tipo |
|----------|---------------|------|
| Monólito modular vs microserviços? | Monólito é mais simples de operar e testar. Microserviços compensam com times independentes e escalas diferentes, mas custam rede, observabilidade e consistência. | D |
| O que é *cache-aside*? | A aplicação consulta o cache; se falhar, busca no banco e grava no cache. Exige estratégia de **invalidação**. | C |
| Quando vale usar uma fila? | Tarefas que podem ser assíncronas, para desacoplar e absorver picos. Custo: consistência eventual e consumidores idempotentes (entrega *at-least-once*). | D |
| Por que 12-factor? | Boas práticas para apps portáveis: config no ambiente, processos stateless, logs em `stdout`, dependências explícitas. | C |
| O que é o GIL? | Em CPython, só uma thread executa bytecode por vez. Atrapalha trabalho de CPU com threads, mas não trabalho de I/O. Para CPU, use processos. | C |
| `async def` vs `def` no FastAPI? | `async def` roda no event loop (não pode bloquear). `def` roda em threadpool. Código bloqueante dentro de `async def` trava todos os requests. | C |
