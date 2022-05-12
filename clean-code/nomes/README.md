# Resumo do livro Clean Code

Atenção aos pequenos detalhes

Códgios representam detalhes dos requisitos, e especificar estes detalhes é programar

# Nomes Significativos

## Use nomes que revelem seu propósito

Deve dizer porque exite, o que faz e como é usado

Contexto deve estar explicito no código

## Evite informações erradas

Evitar dicas que confundam tipo hp para hipotenusa, sendo quepoderiam confundir com sistemas Unix

Usar termos de programação adequadamente, tipo usar "List" em uma varável que não é uma lista

Não usar nomes muito parecidos para variáveis diferentes

## Faça distinções significativas

Programadores muitas vezes criam código voltados apenas para o compilador

Para 2 coisas diferentes no mesmo escopo, por preguiça o programador digita uma delas errada ou diferencia de forma arbitrária as mesmas

Se os nomes precisam ser diferentes é porque possuem significados diferentes

Usar numeros sequencias em nomes, para diferenciar não fornece informação alguma

Não usar palavras muito comuns q nada expressam tipo "ProductInfo" ou "ProductData"

Palavras comuns são redundantes, tipo colocar o nome variável em uma variável e table em um campo de uma tabela

## Use nomes pronunciáveis

Crie nomes produnciáveis, foi como o nosso cerébro evoluiu

Programação é uma atividade social, não poderá discutir sobre tal nome sem parecer um idiota

## Use nomes passíveis de busca

Nomes longos favorecem a busca, pois nomes pequenos acima de tudo letras se repetem muito

Nomes pequenos com só uma letra por exemplo podem ser usados em uma função pequena

O tamanho de um nome deve ser proporcional ao tamanho do seu escopo

## Evite codificações

Nomes codificados raramente são produnciaveis

Adicionam sobrecarga mental

Alem de ser fácil escreve-los incorretamente

## Notação Hungara e afins

Antigamente por limitações das linguagens e dos compiladores, era necessário especificar o tipo nas variáveis

Hoje isso é desnecessário, na verdade isso só atrapalha adicionando informação redundante ao código

Evitar prefixos, eles se tornam obsoletos e ignorados com o tempo, ainda mais hoje que os editores possuem realce de cores

## Interfaces

Não coloque o I na frente dos nomes de interfaces tipo "IShapeFactory", faça "ShapeFactory"

## Evite o mapeamento mental

Use termos do domínio do problema e/ou os da solução

Contador de iterações pode ser uma letra só, já se tornou padrão

Clareza é fundamental

Profissionais usam seus poderes para obem, e escrevem códigos que outros possam entender

## Nomes de classes

Devem ser substantivos

Evitar nomes vagos

## Nomes de métodos

Devem ser verbos

prefixo "set" para métodos de alteração e "get" para métodos de acesso

## Não de uma de espertinho

Não usem gírias ou palavras de baixo calão

Diga o que quer expressar com clareza



