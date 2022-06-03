# O que é monorepositórios

é uma estratégia de desenvolvimento em que o código de várias aplicações fica em um [unico repositório.

# Configuração

Exluir campo main do package.json

Adicionar o campo private como true no package.json

```
  {
    "workspaces": ["sum", "calc"]
  }

  ou 

  "workspaces": {
    "packages": ["packages/*"]
  }
```
yarn add sum@1.0.0


mudar o name do pacote
{
  "name": "@monorepo/calc"
}

{
  "scripts": {
    "start": "yarn workspace @monorepo/calc start"
  }
}