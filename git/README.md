## git init

inicia um repositorio git

```
  git init, transforma pasta atual num repositório
  git init <pasta>, cria uma pasta e cria uma repositório pra ela
```

## git config

```
  git config --global user.name "", define o nome do usuário
  git config --global user.email "", define o email
```

## git status

```
  git status, mostra o status de cada arquivo se está modificado, na area de stage essas coisas.
```

## git logs

```
  git log, exibe os commits por ordem
  git log -n <number_commits>, exibe n commits
  git log --oneline, limita a exibição dos commits a uma linha cada
```

## git add

```
  git add <file ou paste>, adiciona uma pasta ou arquivo na stage área
  git add ., adiciona todos os arquivos e pastas para a stage área
```

## git rm 

```
  git rm <paste or file>, remove o arquivo do controle do git, e deleta localmente
  git rm -r <paste>, remove todos os arquivos de uma pasta de forma recursiva do controle do git, e os deleta localmente
  git rm -r --cache <paste>, remove todos os arquivos de uma pasta de forma recursiva do controle do git, mas não deleta localmente
```

## git diff

```
  git diff, basicamente o que foi modificado desde o último commit
  git diff HEAD~1, o que foi modificado desde o penultimo commit
  GIT diff <commit1> <commit2>, o que foi alterado de um commit1 para um commit 2
```

## git push

```
  git push, manda pro repositório remoto as modificações
  git push -u origin <name_branch>, cria um branch no repositório remoto e manda suas modificações locais
  git push origin --delete <branch_name>, deleta uma branch no repositório remoto
```

## git reset e revert

```
  git revert <commit>, reverte o que um commit anterior fez
  git reset <commit>, exclui todos os commits ate esse commit especificado, porém as modificações são adicionadas na stage área
  git reset --hard <commit> exlui os commits e as modificações até esse commit
```

## git branch

```
  git branch, exibe as brancs do projeto
  git branch <name>, cria uma nova branch
  git branch -d <name>, deleta uma branch local
  git branch -D <name>, deleta uma branch local de forma forçada, udado quando o comando acima não funcina
  git branch -M <name>, renomeia a branch atual
```

## git checkout 

```
  git checkout <commit> <file>, checkout para um arquivo de um commit
  git checkout <tag>
  git checkout <branch>
  git checkout -b <new_branch>, cria uma branch e faz checkout para ela

  git checkout -- <pasta ou file>, reseta uma pasta ou arquivo que não está na stage área
  git checkout -- ., reseta tudo que não está na staged área
  git checkout HEAD -- <pasta ou file>
```

## git tags

criar versões nomeadas de commits

```
  git tag, lista as tags do projeto
  git tag -l "", list as tags cujo nome sigam um padrão
  git tag -a <tag_name> -m "message tag", cria uma tag nomeada, que contém uma descrição
  git tag -a <tag_name> <commit>, cria uma tag apartir de um commit
  git tag <nome_tag>, cria uma tag simples sem descrição
  git push origin <nome_tag>, manda a tag para o repositório remoto
  git push origin --tags, manda todas as tags para o repositório remoto
  git checkout -b [branchname] [tagname], faz checkout para uma branch que é criada apartir de uma branch
```

## git stash

para guardar as modificações que estão no stage área

```
  git stash, guarda as modificações
  git stash list, lista as modificações
  git stash pop, tira as modificações desse aramazenamento provisório e coloca na staged área
```

## git rebase

pode ser usado para transformar vários commits em um commit

```
  git rebase -i <commit>, converter do commit anterior até o atual em um commit só
  git rebase --continue, para quando ocorreu erro no rebase
```

## git commit

```
  git commit, cria um commit e preenche as informações no editor
  git commit -m "message", cria um commit e já define a mensagem
  git commit --amend, mudar a mensagem do commit anterior e a dicionar modificações
  git commit --amend --no-edit, mudar o commit anterior adicionando novas modificações, mas não muda a mensagem
```