# 🛠️ Comandos Essenciais

## Iniciando um Repositório

```bash
git init
# Inicia o Git na pasta atual, criando o repositório local
```

---

## Verificando o Estado

```bash
git status
# Mostra quais arquivos foram modificados, quais estão no stage
# e quais ainda não são rastreados pelo Git

git log
# Exibe o histórico completo de commits (autor, data, mensagem e hash)

git log --oneline
# Versão resumida do log — uma linha por commit, mais fácil de ler

git log --oneline --graph
# Mostra o histórico em forma de árvore, ótimo para visualizar branches

git show <hash>
# Mostra o conteúdo detalhado de um commit específico:
# quais arquivos foram alterados e o que mudou em cada um
```

---

## Comparando Alterações

```bash
git diff
# Mostra o que foi alterado nos arquivos mas ainda NÃO foi para o stage

git diff --staged
# Mostra o que está no stage e será incluído no próximo commit

git diff <hash1> <hash2>
# Compara dois commits específicos
```

---

## Preparando e Salvando Alterações

```bash
git add nome-do-arquivo
# Adiciona um arquivo específico ao stage (prepara para commit)

git add .
# Adiciona TODOS os arquivos modificados ao stage de uma vez

git commit -m "mensagem descritiva"
# Registra permanentemente as alterações que estão no stage
# com uma mensagem explicando o que foi feito
```

> 💡 **Boas mensagens de commit** descrevem *o que* foi feito e *por quê*, não *como*. Ex: `"Adiciona validação de e-mail no formulário de cadastro"`.

---

## Comandos do Terminal (não são do Git)

```bash
touch nome-do-arquivo
# Cria um arquivo vazio (comando do Linux/Mac)
```
