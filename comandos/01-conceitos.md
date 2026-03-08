# 📖 Conceitos Básicos

## O que é Git?

**Git** é um sistema de controle de versão. Ele rastreia todas as alterações feitas nos arquivos de um projeto ao longo do tempo, permitindo voltar a versões anteriores, trabalhar em equipe sem conflitos e manter um histórico completo do desenvolvimento.

---

## Conceitos Fundamentais

### 📸 Commit
Um commit é um **registro permanente de um conjunto de alterações**. Pense nele como uma "fotografia" do estado dos seus arquivos naquele momento.

Cada commit contém:
- As **alterações** feitas nos arquivos
- Uma **mensagem** descrevendo o que foi feito
- **Metadados**: autor, e-mail e data/hora
- Um **hash único** (SHA-1) que o identifica — ex: `a3f5c2d`

---

### 🎭 Stage (Área de Preparação)
Antes de commitar, você precisa **preparar** as alterações. Essa área intermediária se chama *stage* ou *índice*.

```
[ Arquivos editados ] → git add → [ Stage ] → git commit → [ Histórico ]
   (working area)                  (index)
```

Isso permite escolher **exatamente o que** vai entrar em cada commit, mesmo que você tenha alterado vários arquivos.

---

### 🌿 Branch
Uma branch é uma **linha de desenvolvimento independente**. Por padrão, o repositório começa com uma branch chamada `main` (ou antigamente `master`).

Branches são úteis para:
- Desenvolver uma funcionalidade nova sem afetar o código principal
- Trabalhar em equipe sem conflito
- Testar algo antes de integrar ao projeto

---

### 🌐 Repositório Remoto
É a **cópia do repositório hospedada online** (no GitHub, por exemplo). O nome padrão para o repositório remoto principal é `origin` — isso é apenas uma convenção, mas é seguida por quase todo mundo.

---

### 🎯 HEAD
`HEAD` é um **ponteiro que indica em qual commit você está agora**. Normalmente aponta para o último commit da branch atual. Quando você faz um novo commit, o HEAD avança automaticamente.

Você verá o HEAD mencionado em vários comandos como referência ao "estado atual" do repositório.

---

### 🔀 Merge vs Rebase

Ambos servem para integrar o trabalho de uma branch em outra, mas de formas diferentes:

**Merge** — junta os históricos preservando exatamente como aconteceram:
```
main:    A ── B ──────── M  (commit de merge)
                \       /
feature:         C ── D
```

**Rebase** — reaplica os commits de uma branch *em cima* da outra, resultando em um histórico linear:
```
main:    A ── B ── C' ── D'
```

> 💡 Use **merge** para integrar branches de feature ao main. Use **rebase** para manter sua branch atualizada com o main de forma limpa. Evite rebase em branches compartilhadas com outras pessoas.

---

### ⚡ Fast-forward
Quando você faz um merge e a branch principal não teve nenhum commit novo desde que a feature foi criada, o Git simplesmente **move o ponteiro para frente** sem criar um commit de merge. Isso se chama *fast-forward* e resulta em um histórico mais limpo.

---

### 📁 Arquivos Especiais

| Arquivo | Descrição |
|---|---|
| `.gitignore` | Lista arquivos e pastas que o Git deve **ignorar** (ex: senhas, `.env`, `node_modules`) |
| `.gitkeep` | Arquivo vazio criado para **forçar o Git a rastrear uma pasta vazia** (o Git ignora diretórios sem arquivos) |
