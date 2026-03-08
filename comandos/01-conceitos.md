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

### 📁 Arquivos Especiais

| Arquivo | Descrição |
|---|---|
| `.gitignore` | Lista arquivos e pastas que o Git deve **ignorar** (ex: senhas, `.env`, `node_modules`) |
| `.gitkeep` | Arquivo vazio criado para **forçar o Git a rastrear uma pasta vazia** (o Git ignora diretórios sem arquivos) |
