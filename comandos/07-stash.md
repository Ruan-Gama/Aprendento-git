# 🗄️ Stash

O stash é uma **área temporária** onde você pode guardar alterações que ainda não estão prontas para um commit. Útil quando você precisa trocar de branch rapidamente sem perder o que estava fazendo.

---

## Comandos

```bash
git stash
# Guarda todas as alterações não commitadas em uma pilha temporária
# e deixa o diretório limpo (como estava no último commit)

git stash push -m "descrição do que estava fazendo"
# Guarda o stash com um nome descritivo — muito mais fácil de identificar depois

git stash list
# Lista todas as alterações guardadas no stash
# Exemplo de saída:
# stash@{0}: WIP on main: a3f5c2d mensagem do commit
# stash@{1}: On feature: minha descrição aqui

git stash pop
# Recupera as alterações mais recentes do stash e as remove da lista

git stash apply stash@{1}
# Recupera um stash específico da lista, mas o MANTÉM salvo
# Útil se quiser aplicar o mesmo stash em mais de uma branch

git stash drop stash@{0}
# Remove um stash específico da lista sem aplicá-lo

git stash clear
# Remove TODOS os stashes salvos de uma vez
# ⚠️ Irreversível
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
