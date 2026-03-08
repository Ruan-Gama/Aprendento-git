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
```

> 💡 Versões mais recentes do Git têm o `git switch` como alternativa mais clara ao `git checkout` para trocar de branch.

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

## Resumo do Fluxo com Branches

```
main ─────────────────────────────────────────► (produção)
          \                          /
    feature ──── commits ── commits ── (merge de volta)
```
