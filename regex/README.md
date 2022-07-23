# REGEX - Expressões Regulares

Expressões regulares são usadas em linguagens de programação para encontrara e extrair partes de strings que obedecem a um padrão específico.

Expressões regulares no geral obedecem ao seguinte formato /padrao/opcoes, onde padrao é uma expressão regular, e option é um conjunto de opções para complementar a regex.

Para testar se um padrãp ocorre em uma string utilizamos o método test  da regex que retorna true se o padrão conseguir ser identificado, ou false caso contrário, conforme ilustrado no código abaixo:

```
  const testeString = 'Anderson legal!!!'
  const testeRegex = /Anderson/
  testeRegex.test(testeString)
```

## Criar correspondencia de strings literais

O padrão será formado pela string que está na regex de forma literal, se for colocado variações de forma miúscula ou minúscula, o padrão não será identificado. Um exemplo é utilizar o padrão /Anderson/, ele não irá identificar "ANDERSON" ou "anderson" por exemplo, porque não está exatamento igual que seria "Anderson"

## Buscar uma string literal com diferentes possibilidades

É possível procurar por diversos padrões de uma vez só, utilizando o operador de alternação |. Ficaria algo como /Anderson|anderson|ANDERSON/, o método teste irá retornar true se encontrar pelo menos um dos padrões.

## Ignorar maiúsculas de minúsculas

Para ignorar a diferenciação de maiúsculas de minúsculas é só usar a opçao i apos a regex:

```
/anderson/i
```

## Extrair resultados

Para extrair os resultados da verificações dos padrões, ou as correspondências, é só usar o método match() das strings e passar como parâmetro uma regex:

```
  const regex = /Anderson/i
  const testString = "anderson amigo legal!!!"
  testString.match(regex)
```

## Extrair mais de um resultado

Para extrair mais de um resultado que corresponde ao padrão é necessário colocara a flag g, que indica procurar o padrão de forma global:

```
const regex = /Anderson/gi
const str = "Anderson, anderson oi oi"
str.match(str)
```

## Caractere coringa

O caractere curinga representado pelo ., representa qualquer caractere e é bastante util em padões que possuem partes fixas ou caracteres já ,conhecidos e outros variáveis:

```
  const regex = /ander./gi
  const str = "anderson"
  str.match(regex)
```

## Classes de caracteres

Temos 2 extremos ja comentados, /regex/, que encontra a string literal da regoex nada variável, e /./ que corresponde a qualquer coisa e portanto o mais variável possível. Ma podemos montar algo intermediário para corresponder um certo grupo de caracteres por meio das classses de caracteres. Com o [aeio] estamos especificando que será um desses caracteres que serão capturados. Por exemplo a regex /ander[aei]/ corresponde as strings "andersa", "anderse" e "andersi" 

```
  const regex = /ander[aio]/gi
  const str = "andero"
  str.match(regex)
```

## Intervalo de caracteres em classes

Podemos usar o hifen nas classes para definir qual intervalo de caracteres é válido. Por exemplo /[a-d]oi/ corresponde as strings "aoi", "boi", "coi" e "doi"

```
  const regex = /[a-d]oi/gi
```

intervalos convencionais:
- [a-z]
- [A-Z]
- [0-9]
- [a-z0-9]

## Classe de caracteres negada

server para capturar correspondencias que não contenham esse padrão. Isso é feito utilizando se o acento circunflexo no início do padrão da classe. Por exemplo /[^oi]la/gi, as strings "ola" e "ila" não serão capturas, mas "ala" será:

```
  const regex = /[^oi]la/
  const str = "ala"
  str.match(regex)
```

## Capturar caracteres que aparecem uma ou mais vezes

Podemos usar o caractere de + após o caractere ou classe que ele vai identificar asequencia de forma repetida 1 ou mais vezes

* 

## Captura ganaciosa x Captura preguiçosa

Por padrão as regex capturam de forma gulosa, elas vão procurar as maiores correspondências que cumprem o padrão especificado. Já a captura preguiçosa encontra o menor pedaço da string que satisfaza o padrão. Precisa-se apenas adicinar o ? após o padrão para especificar que ele deve ser encontrado de forma preguiçosa. Dessa forma a regex /anders[aeiou]*?n/ pode corresponder a vários padrões como "anderson", "andersn" e "andersuoiiiiiin", mas se todos esses padroes estiverem na string, o método match irá retornar apenas "andersn" já q é o menor

```
  const regex = /anders[aeiou]*?n/
  const str = "anderson andersn andersuoiiiiiin"
  const str.match(regex)
```

## Buscar no início e fim das strings

O ^ fora de classes e no começo da regex testa se a string começa com aquele padrão:

```
  const regex = /^lalala/
  const str = "lalala oi amigo"
  regex.test(str)
```

O $ fora de classes e no final da regex testa se a string termina com aquele padrão:

```
  const regex = /lalala$/
  const str = "oi amigo lalala"
  regex.test(str)
```

## Forma reduzidas de classes de caracteres comuns

- \w: equivalente a todas as letras do alfabeto com o _ ([A-Za-z0-9])

- \W: contrário ap \w, pega tudo que não é alphanumérico nem _ ([^A-Za-z0-9])

- \d: pega todos os números ([0-9])

- \D: contrário do \d, pega tudo que não é número ([^0-9])

- \s: captura os espaços em branco, tabulações, scapes e quebras de linha, ([\r\t\f\n\v])

- \S: captura tudo que não é os espaços em branco, tabulações, scapes e quebras de linha, ([^\r\t\f\n\v])

## Especificar o número de capturas de uma classe

Vimos os caracteres especiais + e * que capturam 1 ou mais ocorrencia, e 0 ou mais ocorrencias respectivamente. Podemos especificar o número extao de ocorrências. Para fazer isso colocamos {} após o padrão, e colocamos o número mínimo e máximo de ocorrências.

- /padrao{min,max}/, especifica o mínmo e o máximo

- /padrao{min,}/, especifica apenas o mínimo

- /padrao{,max}/, especifica apenas o máximo

- /padrao{qtde}/, especifica um número exato e fixo de vezes

## Padrões opcionais

O caractere ? após o padrão especifica que ele é opcional, e portanto pode ocorrer 0 ou 1 vez:

```
  const regex = /andersoo?n/gi
  const str = "anderson andersoon"
  str.match(regex)
```

## lookaheads positivos e negativos

Lookaheads ("olhar à frente") são padrões que pedem ao javascript para procurar outros padrões sem captura-los, eles só validam o padrão, mas não fazem parte do retorno.

Lookageads positivos verificam se o padrão existe a sua frente, e usa-se (?=...), onde ... é o padrão

Lookaheads negativas verificam se o padrão não existe a sua frente, usa-se (?!...), onde ... é o padrão.

## Grupos de caracteres

Usa-se (...|...) e o operador de alternação. Podemos criar regex como /ander(son|sen|sin)/ que corresponde a "anderson", "andersen" e "andersin"

## Grupo de captura 

São usado para capturar substrings repetidas. Primeiro devemos envolver o padrão da substring entre parênteses, em seguida deve se colocar uma barra repetida com a numero da ordem desse padrão na na regex algo como \1.

## Regex para procurar e substituir em strings

Deve-se utilizar o método replace que recebe como parametro uma regex e o texto que irá substituir a regex, também é possivel acessar grupos de caracteres na string de substituição:

```
  let wrongText = "The sky is silver.";
  let silverRegex = /silver/;
  wrongText.replace(silverRegex, "blue");

  "Code Camp".replace(/(\w+)\s(\w+)/, '$2 $1')
```
