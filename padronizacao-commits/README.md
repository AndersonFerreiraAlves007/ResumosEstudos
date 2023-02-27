# Padronização de commits

yarn add @commitlint/config-conventional @commitlint/cli -D

echo "module.exports = { extends: ['@commitlint/config-conventional'] };" > commitlint.config.js

yarn add husky -D

yarn husky install

"scripts": {
  "prepare": "husky install"
}

yarn husky add .husky/commit-msg 'yarn commitlint --edit $1'

yarn add commitizen -D

yarn commitizen init cz-conventional-changelog --yarn --dev --exact

"scripts": {
  "commit": "git-cz"
}

# Formato

!type(?scope): !subject
<?body>
<?footer>

“If applied, this commit will <message>”

test: indica qualquer tipo de criação ou alteração de códigos de teste. Exemplo: Criação de testes unitários.
feat: indica o desenvolvimento de uma nova feature ao projeto. Exemplo: Acréscimo de um serviço, funcionalidade, endpoint, etc.
refactor: usado quando houver uma refatoração de código que não tenha qualquer tipo de impacto na lógica/regras de negócio do sistema. Exemplo: Mudanças de código após um code review
style: empregado quando há mudanças de formatação e estilo do código que não alteram o sistema de nenhuma forma.
Exemplo: Mudar o style-guide, mudar de convenção lint, arrumar indentações, remover espaços em brancos, remover comentários, etc..
fix: utilizado quando há correção de erros que estão gerando bugs no sistema.
Exemplo: Aplicar tratativa para uma função que não está tendo o comportamento esperado e retornando erro.
chore: indica mudanças no projeto que não afetem o sistema ou arquivos de testes. São mudanças de desenvolvimento.
Exemplo: Mudar regras do eslint, adicionar prettier, adicionar mais extensões de arquivos ao .gitignore
docs: usado quando há mudanças na documentação do projeto.
Exemplo: adicionar informações na documentação da API, mudar o README, etc.
build: utilizada para indicar mudanças que afetam o processo de build do projeto ou dependências externas.
Exemplo: Gulp, adicionar/remover dependências do npm, etc.
perf: indica uma alteração que melhorou a performance do sistema.
Exemplo: alterar ForEach por while, melhorar a query ao banco, etc.
ci: utilizada para mudanças nos arquivos de configuração de CI.
Exemplo: Circle, Travis, BrowserStack, etc.
revert: indica a reverão de um commit anterior.

O modo imperativo significa apenas “falado ou escrito como se estivesse dando um comando ou instrução”

Uma linha de assunto de confirmação do Git devidamente formada deve sempre ser capaz de completar a seguinte frase :

Se aplicado, este commit será sua linha de assunto aqui

fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: #123
BREAKING CHANGE: use JavaScript features not available in Node 6.
