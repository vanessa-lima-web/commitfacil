# Contribuindo

Obrigada por querer ajudar! 💜

## Como rodar localmente

```bash
git clone https://github.com/SEU_USUARIO/commitfacil.git
cd commitfacil
npm link          # deixa o comando `commitfacil` disponível global
npm test
```

## Padrão de commits

Este projeto usa Conventional Commits — e a ferramenta faz isso por você:

```bash
git add .
commitfacil
```

## Fluxo de PR

1. Crie uma branch: `git checkout -b feat/minha-ideia`
2. Faça a mudança e adicione teste se for lógica nova
3. Rode `npm test` (tem que passar)
4. Abra o Pull Request descrevendo o que mudou
