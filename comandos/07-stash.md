# 🗄️ Stash

O stash é uma **área temporária** onde você pode guardar alterações que ainda não estão prontas para um commit. Útil quando você precisa trocar de branch rapidamente sem perder o que estava fazendo.

---

## Comandos

```bash
git stash
# Guarda todas as alterações não commitadas em uma pilha temporária
# e deixa o diretório limpo (como estava no último commit)

git stash list
# Lista todas as alterações guardadas no stash
# Exemplo de saída:
# stash@{0}: WIP on main: a3f5c2d mensagem do commit
# stash@{1}: WIP on feature: b7e1d4a outra mensagem

git stash pop
# Recupera as alterações mais recentes do stash e as remove da lista

git stash apply
# Recupera as alterações mais recentes do stash, mas as MANTÉM na lista
# Útil se quiser aplicar o mesmo stash em mais de uma branch
```

---

## Quando usar?

**Cenário típico:**

1. Você está no meio de uma funcionalidade na branch `feature`
2. Surge uma correção urgente que precisa ser feita na `main`
3. Você não quer commitar um trabalho incompleto

```bash
# Salva o trabalho em progresso
git stash

# Troca de branch e faz a correção
git checkout main
# ... faz as alterações e commita ...

# Volta para sua branch e recupera o trabalho
git checkout feature
git stash pop
```
