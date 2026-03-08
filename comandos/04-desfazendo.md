# ↩️ Desfazendo Alterações

## Removendo do Stage

```bash
git reset nome-do-arquivo
# Remove o arquivo do stage, mas mantém as alterações no arquivo

git restore --staged nome-do-arquivo
# Faz a mesma coisa — é o comando mais moderno para isso
```

---

## Descartando Alterações

```bash
git restore nome-do-arquivo
# Descarta as alterações não salvas do arquivo,
# voltando para como ele estava no último commit
# ⚠️ Cuidado: as alterações são perdidas permanentemente
```

---

## Editando o Último Commit

```bash
git commit --amend -m "nova mensagem aqui"
# Substitui a mensagem do último commit por uma nova
# ⚠️ Só use isso se o commit ainda NÃO foi enviado ao repositório remoto
```

---

## Voltando para um Commit Anterior (git reset)

Primeiro, descubra o hash do commit com `git log`. Então escolha o modo:

```bash
git reset --soft <hash>
# Volta para o commit indicado
# ✅ Mantém os arquivos no disco
# ✅ Mantém as alterações no stage (prontas para commit)

git reset --mixed <hash>
# Volta para o commit indicado (comportamento padrão)
# ✅ Mantém os arquivos no disco
# ❌ Remove as alterações do stage (precisa rodar git add novamente)

git reset --hard <hash>
# Volta para o commit indicado completamente
# ❌ Apaga todas as alterações feitas após aquele commit
# ⚠️ Irreversível — use com muito cuidado
```

---

## Visualizando o Histórico Completo

```bash
git reflog
# Mostra TODO o histórico de ações, incluindo resets e checkouts
# Útil para recuperar commits "perdidos" após um reset --hard
```

---

## Resumo Visual

```
--soft  → volta o ponteiro    [ stage intacto  | arquivos intactos ]
--mixed → volta o ponteiro    [ stage limpo    | arquivos intactos ]
--hard  → volta o ponteiro    [ stage limpo    | arquivos apagados ]
```
