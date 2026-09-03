# 🚀 CommitFácil

> CLI interativa em português pra criar **Conventional Commits** sem complicação.

Nunca mais trave na hora de escrever `feat`, `fix`, `docs` ou `chore`. O CommitFácil te guia com perguntas simples e monta a mensagem no padrão certo automaticamente.

![Node](https://img.shields.io/badge/node-%3E%3D18-green)
![License](https://img.shields.io/badge/license-MIT-blue)

---

## ✨ Por que usar

Escrever commit padronizado é chato quando você tá começando: "isso é `feat` ou `chore`? preciso de escopo? cadê o `!`?". O CommitFácil resolve isso perguntando em PT-BR e cuidando da formatação pra você.

- ✅ Menu de tipos com explicação de cada um
- ✅ Detecta os arquivos em stage automaticamente
- ✅ Monta escopo, corpo e `BREAKING CHANGE`
- ✅ Valida o tamanho e o estilo do cabeçalho
- ✅ **Zero dependências** — só Node puro

## 📦 Instalação

```bash
# Uso pontual, sem instalar:
npx commitfacil

# Ou instale global:
npm install -g commitfacil
```

## 🎬 Como usar

Dentro de qualquer repositório git, depois de dar `git add`:

```bash
commitfacil
```

E responda as perguntas:

```
🚀 CommitFácil — commits padronizados sem complicação

📂 Arquivos que vão pro commit:
   M  src/header.jsx

Qual o tipo dessa mudança?
   1. ✨ feat  — nova funcionalidade pro usuário
   2. 🐛 fix   — correção de bug
   ...

Escolha o número: 1
Escopo (opcional): header
Descrição curta: adiciona menu responsivo

──────────── Prévia ────────────
feat(header): adiciona menu responsivo
────────────────────────────────

Confirmar commit? [S/n]: s
✅ Commit criado com sucesso!
```

## 🧠 Os tipos (Conventional Commits)

| Tipo | Quando usar |
|------|-------------|
| `feat` | nova funcionalidade |
| `fix` | correção de bug |
| `docs` | só documentação (README, comentários) |
| `style` | formatação, sem mudar lógica |
| `refactor` | refatora sem corrigir bug nem add feature |
| `perf` | melhoria de performance |
| `test` | adiciona ou ajusta testes |
| `build` | build, dependências |
| `ci` | configuração de CI |
| `chore` | tarefa que não mexe em src nem teste |
| `revert` | reverte um commit |

Baseado na spec oficial: [conventionalcommits.org](https://www.conventionalcommits.org).

## 🏗️ Arquitetura

Separação em camadas pra ficar testável e fácil de manter:

```
src/
├── core/            # lógica PURA (sem I/O) — o coração testável
│   ├── commit-types.js    # definição dos tipos
│   └── build-message.js   # monta e valida a mensagem
├── git/             # integração com o git (child_process)
│   └── git.js
└── cli/             # interação com o usuário
    ├── prompt.js          # perguntas no terminal
    └── run.js             # orquestra o fluxo
bin/
└── commitfacil.js   # executável (#!/usr/bin/env node)
test/
└── build-message.test.js  # testes da lógica pura
```

**Princípio:** o `core` não sabe o que é terminal nem git. Isso deixa a lógica 100% testável sem mockar nada.

## 🧪 Testes

```bash
npm test
```

Usa o test runner nativo do Node (`node --test`) — sem Jest, sem config.

## 🤝 Contribuindo

Veja [CONTRIBUTING.md](./CONTRIBUTING.md). E claro: use o próprio CommitFácil pra commitar aqui 😄

## 📄 Licença

MIT © Vanessa Rafaella
