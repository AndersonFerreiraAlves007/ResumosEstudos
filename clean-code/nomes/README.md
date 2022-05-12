# Nomes Significativos

## Use nomes que revelem seu propósito

Os nomes devem dizer porque exitem, o que fazem e como são usados;

Contexto deve estar explícito no código;

## Evite informações erradas

Evitar dicas que confundam tipo "hp" para hipotenusa, sendo que poderiamconfundir com sistemas Unix;

Usar termos de programação adequadamente, tipo usar "List" em uma variável que não é uma lista seria errado;

Não usar nomes muito parecidos para variáveis diferentes;

## Faça distinções significativas

Programadores muitas vezes criam código voltados apenas para o compilador;

Para 2 coisas diferentes no mesmo escopo, por preguiça o programador digita uma delas errada ou diferencia de forma arbitrária as mesmas;

Se os nomes precisam ser diferentes é porque possuem significados diferentes;

Usar números sequencias em nomes para diferenciar, não fornece informação alguma;

Não usar palavras muito comuns que nada expressam, tipo "ProductInfo" ou "ProductData";

Palavras comuns são redundantes, tipo colocar o nome "variável" em uma variável ou "table" em um campo de uma tabela;

## Use nomes pronunciáveis

Crie nomes pronunciáveis, foi como o nosso cerébro evoluiu;

Programação é uma atividade social, não poderá discutir sobre tal nome sem parecer um idiota;

## Use nomes passíveis de busca

Nomes longos favorecem a busca, pois nomes pequenos acima de tudo letras se repetem muito;

Nomes pequenos com só uma letra por exemplo, podem ser usados em uma função pequena;

O tamanho de um nome deve ser proporcional ao tamanho do seu escopo;

## Evite codificações

Nomes codificados raramente são pronunciáveis;

Adicionam sobrecarga mental, por ter que se esforçar para codifica-los;

Além de ser fácil escreve-los incorretamente;

## Notação Húngara e afins

Antigamente por limitações das linguagens e dos compiladores, era necessário especificar o tipo no nome das variáveis;

Hoje isso é desnecessário, na verdade isso só atrapalha adicionando informação redundante ao código;

Evitar prefixos, eles se tornam obsoletos e ignorados com o tempo, ainda mais hoje que os editores possuem realce de cores;

## Interfaces

Não coloque o "I" na frente dos nomes de interfaces tipo "IShapeFactory", faça "ShapeFactory";

Não queremos criar distição entre classes e interfaces, pelo contrário queremos que quem usa o código trate todas as classe que inplementam a interface como se fosse a própria interface;

## Evite o mapeamento mental

Use termos do domínio do problema e/ou os da solução;

Contador de iterações pode ser uma letra só, já se tornou padrão;

Clareza é fundamental;

Profissionais usam seus poderes para o bem, e escrevem códigos que outros possam entender;

## Nomes de classes

Devem ser substantivos;

Evitar nomes vagos;

## Nomes de métodos

Devem ser verbos;

Prefixo "set" para métodos de alteração e "get" para métodos de acesso;

## Não dê uma de espertinho

Não usem gírias ou palavras de baixo calão;

Diga o que quer expressar com clareza;

## Use nomes a partir do domínio da solução

São programadores que lerão seu código, lembre-se disso;

Use termos de informática, algoritmos, padrões e termos matemáticos;

Companheiros não precisam consultar o cliente para saber o significado de um nome que eles já conhecem o conceito;

Selecionar nomes técnicos é na maioria das vezes mais adequado;

## Use nomes do domínio do problema

Se não puder usar termos técnicos ou do domínio da solução, use termos do domínio do problema;

Pelo menos o programador que faz a manutenção, poderá consultar um especialista;

## Adicione um contexto significativo

Nomes na maioria das vezes não são significativos por si só;

Por exemplo métodos, eles tem como contexto as suas classes;

Além disso um conjunto de variáveis juntas, podem formar um contexto também, tipo o endereço com seus campos;

Outra forma de adicionar contexto é adicionar prefixo, porém esse form não é muita adequada, use a em último caso;

## Não adicione contextos desnecessários

Por exemplo adicionar o mesmo prefixos em várias classes, estaria trabalhando contra ferramentas de busca por exemplo;

Nomes curtos são preferíveis desde que sejam claros;

## Conclusão

Construir bons nomes envolve:

- Boas habilidades de descrição;
- Histórico cultural compartilhado;
- É uma questão de aprender;

Não deve-se ter medo de renomear coisas, por outros desenvolvedores serem contra;

Vale a pena em longo prazo;
