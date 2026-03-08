# 🌐 Repositório Remoto

## Conectando ao GitHub

```bash
git remote add origin https://github.com/usuario/repositorio.git
# Conecta o repositório local a um remoto
# "origin" é o apelido dado ao endereço remoto — é uma convenção universal
```

---

## Enviando Alterações

```bash
git push
# Envia os commits locais para o repositório remoto
# (só funciona após o vínculo abaixo ter sido feito)

git push -u origin nome-da-branch
# Envia e cria o vínculo entre a branch local e a remota
# Após usar -u uma vez, basta usar "git push" nas próximas vezes
```

> 💡 `-u` significa `--set-upstream`. Você só precisa usá-lo na **primeira vez** que envia uma branch.

---

## Recebendo Alterações

```bash
git pull
# Baixa as alterações do repositório remoto e já integra ao local
# É equivalente a: git fetch + git merge

git fetch origin nome-da-branch
# Baixa as alterações do remoto, mas NÃO integra automaticamente
# Útil para revisar o que mudou antes de fazer o merge
```

---

## Clonando um Repositório

```bash
git clone https://github.com/usuario/repositorio.git
# Cria uma cópia local completa de um repositório remoto

git clone https://github.com/usuario/repositorio.git --branch nome-da-branch --single-branch
# Clona apenas uma branch específica (útil para repositórios grandes)
```

---

## ⚠️ Conflito de Push

Se outra pessoa fez push enquanto você trabalhava, o Git vai recusar seu envio:

```
! [rejected] main -> main (fetch first)
```

**Solução:**

```bash
# 1. Atualize o repositório local
git pull

# 2. O Git tentará fazer o merge automaticamente.
#    Se houver conflito, ele vai marcar os arquivos assim:

<<<<<<< HEAD
  sua versão do código
=======
  versão do remoto
>>>>>>> origin/main

# 3. Edite o arquivo, escolha qual versão manter (ou combine as duas)
# 4. Salve, adicione ao stage e commite

git add nome-do-arquivo
git commit -m "resolve conflito de merge"

# 5. Agora pode fazer o push normalmente
git push
```
