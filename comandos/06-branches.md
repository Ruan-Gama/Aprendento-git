# 🌿 Branches

Branches permitem trabalhar em funcionalidades isoladas sem afetar o código principal. O fluxo mais comum é: criar uma branch para cada feature ou correção, e depois mesclar de volta à `main`.

---

## Listando e Inspecionando

```bash
git branch
# Lista todas as branches locais
# A branch atual aparece marcada com *

git branch -v
# Lista todas as branches com o hash e mensagem do último commit de cada uma
```

---

## Criando e Trocando de Branch

```bash
git checkout -b nome-da-branch
# Cria uma nova branch e já troca para ela
# Se já existir uma com esse nome, retorna um erro

git checkout nome-da-branch
# Troca para uma branch já existente

# Alternativa moderna (Git 2.23+):
git switch nome-da-branch        # troca para uma branch existente
git switch -c nome-da-branch     # cria e troca para uma nova branch
```

> 💡 `git switch` foi criado para substituir o `git checkout` na função de trocar de branch, deixando o comando com uma responsabilidade só. Prefira `switch` em projetos novos.

---

## Renomeando

```bash
git branch -m novo-nome
# Renomeia a branch atual
```

---

## Mesclando Branches (Merge)

```bash
# Primeiro, vá para a branch que vai RECEBER as alterações
git checkout main

# Depois mescle a branch desejada
git merge nome-da-branch
# Integra os commits da outra branch na branch atual
```

> 💡 Se as duas branches alteraram o mesmo trecho do mesmo arquivo, o Git vai gerar um **conflito de merge** que você precisa resolver manualmente (igual ao conflito de push remoto).

---

## Comparando Branches

```bash
git diff branch-1 branch-2
# Mostra as diferenças entre duas branches linha por linha
```

---

## Deletando

```bash
git branch -d nome-da-branch
# Deleta a branch (só funciona se ela já foi mesclada)
# Use -D para forçar a exclusão mesmo sem merge
```

---

## Rebase

```bash
# Estando na branch feature:
git rebase main
# Reaplica os commits da branch atual em cima do último commit do main
# Resultado: histórico linear, sem commits de merge

# ⚠️ Nunca faça rebase de uma branch que já foi enviada ao remoto
# e que outras pessoas estão usando — isso reescreve o histórico
```

---

## Cherry-pick

```bash
git cherry-pick <hash>
# Aplica um commit específico de qualquer branch na branch atual
# Útil quando você quer trazer apenas uma alteração pontual,
# sem fazer o merge da branch inteira
```

---

## Resumo do Fluxo com Branches

```
main ─────────────────────────────────────────► (produção)
          \                          /
    feature ──── commits ── commits ── (merge de volta)
```
