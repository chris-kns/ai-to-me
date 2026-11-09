# Fase 1 — Base DevOps/SRE (Semanas 1 a 4)

> ← [Voltar ao plano](README.md) · Marque `[x]` ao concluir cada semana.

**Ritmo:** 1 h por dia, de segunda a sábado (domingo livre) | **Regra 1:1** — cada hora de conteúdo = 1 hora escrevendo código

### Semana 1: Python — fundamentos e como a linguagem pensa
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Variáveis, tipos, condicionais e loops |
| Ter | Funções e escopo |
| Qua | Listas, tuplas, sets e dicionários |
| Qui | Exceções, módulos e arquivos |
| Sex | venv, pacotes e orientação a objetos básica |
| **Sáb** | **Mini projeto: escolha um e construa do zero** |

**Mini projetos sugeridos:** conversor de moeda · gerenciador de tarefas no terminal · sistema simples de cadastro · leitor de arquivo · jogo no terminal

> 📎 **Itens que o roteiro não citava, mas aparecem em todo código real:** f-strings, list/dict comprehensions, `with open(...)`, `pathlib`, `json`, `datetime`, `enumerate`/`zip`, `*args`/`**kwargs`.

**Exercícios (1 por conceito):** [exercicios/fase-1/semana-01-python.md](../exercicios/fase-1/semana-01-python.md) · **Pegadinhas:** [fundamentos/pegadinhas-python.md](../fundamentos/pegadinhas-python.md)

> 🧪 **Autoteste:** fecha o material, abre o arquivo vazio. Consegue escrever uma função? Um dicionário? Um loop? Se não, ainda não aprendeu — reconheceu.

> 💡 Nesse primeiro mês você não está construindo portfólio. Está construindo **fundamentos** e aprendendo a tomar decisões.

**Entrega:** mini projeto em Python funcionando.

---

### Semana 2: Git, organização de projeto e engenharia básica
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Git: init, add, commit, branches, merge, rebase |
| Ter | GitHub: push, pull, PR, issues; commits detalhados (Conventional Commits) e auto-revisão do próprio PR |
| Qua | Ambiente virtual, dependências e `pyproject.toml` |
| Qui | Tipagem (`type hints`), tratamento de erros e `logging` |
| Sex | Debugging (`print`, `pdb`, breakpoints) e organização de arquivos |
| **Sáb** | **Projeto estruturado com .git, README, testes e arquivos separados** |

**Projetos sugeridos:** sistema de biblioteca · controle de despesas · sistema de estoque

> ⚠️ A pergunta **"Por que eu organizei assim?"** precisa ter resposta clara. Decisões precisam ser sempre fundamentadas.

> 💡 Ninguém te contrata para escrever `for` e `if`. No mercado, você interage com projetos, toma decisões, presta suporte e revisa código dos outros.

**Entrega:** projeto pequeno com estrutura, testes, .git e readme.md.

---

### Semana 3: Docker e CI/CD
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Docker: conceitos, imagens, containers |
| Ter | Dockerfile e multi-stage builds |
| Qua | Docker Compose: múltiplos serviços |
| Qui | GitHub Actions: pipeline básica (lint + testes) |
| Sex | `pre-commit`, `ruff` e automação de qualidade |
| **Sáb** | **Pipeline CI verde rodando no repositório** |

**Entrega:** repositório com pipeline CI/CD e imagem Docker.

---

### Semana 4: Ansible, Prometheus, Grafana e SLOs
- [ ] Concluída

| Dia | Tópico |
|-----|--------|
| Seg | Ansible: inventário e playbooks básicos |
| Ter | Ansible: roles e automação de configuração |
| Qua | Prometheus: métricas, scraping e PromQL |
| Qui | Grafana: dashboards e alertas |
| Sex | SLOs: conceito e definição |
| **Sáb** | **Stack de monitoramento rodando + repositório base da API** |

> ⚠️ **Semana pesada (5 dias, 4 ferramentas).** Se apertar, a ordem de prioridade é: Prometheus + Grafana + SLOs (conhecimento-chave de SRE) → Ansible básico (inventário + 1 playbook) → Ansible roles. Roles pode escorregar para o sábado. O que não pode faltar na entrega: a stack de monitoramento rodando.

**Entrega:** stack de monitoramento rodando + repositório base da API de inventário.
