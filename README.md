# 📘 Meu Caderno de Git

Anotações pessoais de estudo sobre Git e GitHub — do básico ao fluxo de trabalho com branches e repositórios remotos.

---

## 📂 Estrutura

| Arquivo | Conteúdo |
|---|---|
| [01 - Conceitos Básicos](./comandos/01-conceitos.md) | O que é Git, commit, stage, branch... |
| [02 - Configuração](./comandos/02-configuracao.md) | Configurar nome, e-mail e escopo |
| [03 - Comandos Essenciais](./comandos/03-essenciais.md) | init, add, commit, status, log |
| [04 - Desfazendo Alterações](./comandos/04-desfazendo.md) | restore, reset, amend, reflog |
| [05 - Repositório Remoto](./comandos/05-remoto.md) | push, pull, fetch, clone, remote |
| [06 - Branches](./comandos/06-branches.md) | Criar, trocar, mesclar e deletar branches |
| [07 - Stash](./comandos/07-stash.md) | Guardar alterações temporariamente |

---

## ⚡ Fluxo de Trabalho Básico

```bash
# 1. Inicia o repositório
git init

# 2. Edita seus arquivos...

# 3. Prepara as alterações
git add .

# 4. Salva um commit
git commit -m "mensagem descritiva"

# 5. Envia para o GitHub
git push
```

---

> 💡 **Dica:** use `git status` sempre que tiver dúvida sobre o estado atual do repositório.
