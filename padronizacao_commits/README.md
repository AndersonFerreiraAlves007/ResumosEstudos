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

