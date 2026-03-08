# ⚙️ Configuração

Antes de usar o Git, é necessário informar quem você é. Essas informações aparecem em cada commit que você fizer.

---

## Comandos

```bash
# Define o nome do usuário
git config --global user.name "Seu Nome"

# Define o e-mail do usuário
git config --global user.email seuemail@exemplo.com

# Exibe todas as configurações ativas
git config --list
```

---

## Escopos de Configuração

| Escopo | Flag | Onde se aplica |
|---|---|---|
| Global | `--global` | Todos os repositórios do seu usuário no sistema |
| Local | `--local` | Apenas o repositório atual (sobrescreve o global) |
| Sistema | `--system` | Todos os usuários da máquina |

> 💡 Na maioria dos casos, `--global` é o suficiente. Use `--local` quando precisar de um nome/e-mail diferente em um projeto específico.
