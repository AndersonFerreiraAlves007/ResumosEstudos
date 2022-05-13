# Funções

## Pequenas

Funções devem ser pequenas;

É bom que a função não seja maior que a tela;

Máximo 150 caracteres por linha;

Funções no máximo 100 linhas, recomendado mesmo é 20 linhas;

# Blocos e Endentação

Blocos devem ter apenas uma linha, de preferencia uma chamada de função;

O fato de chamar uma função, fornece uma nome segnificativo para a operação;

Funções não devem ser grandes demais, nem ter muitas estruturas aninhadas;

Nível de endentação de uma função deve ser no máximo de 1 ou 2;


# Faça apenas uma coisa

É difícil dizer o que é uma coisa;

Verificar se é possível extrair outra função apartir de seu nome;

Se uma função faz todos aqueles passos em um nível abaixo do nome da função, então ela faz uma coisa só;

# Seções dentro de funções

Se sua função divide o código em seções, é porque ela não uma única coisa;

# Um nível de abstração por função

Não misturar conceitos a detalhes;

# Ler o código de cima para baixo (regra decrescente)

Ler como uma narrativa;

Ler o programa como uma série de parágrafos To;

Cada To descrevendo o nível atual, e fazendo referências aos parágrafos TO consecutivos no próximo nível;

# Estrutura Switch

# Use nomes descritivos

Você sabe que está criando um código limpo, quando cada rotina que voc~e lê é como você esperava;

Quanto menor a função, mais fácil escolher seu nome;

Seja consistente, use os mesmos verbos, substantivos, frases nas funções de um mesmo módulo;

# Parâmetros de funções

O ideal é 0;

Pode ter até 2 (mônade ou díade) mas evitar ao máximo 3 ou mais (triade);

É ruim até pros testes, pois tem que testar diversas combinações de parâmetros;

# Funções Mônades

Eficar transformar o valor recebido como paramaetro

# Parâmetros Lógicos

Funções que recebem booleanos como parâmetros passam a impressão que fazem mais de uma coisa

# Funções Díades

Use quando tiver uma ordem predeterminada natural;

Quando forem componentes de m único fator;

# Evite efeitos colaterais

Efeitos colaterais são mentiras;

Função promete algo, e faz outras escondidas;

# Parâmetros de saída

Nunca forçar o leitor a ler a assinatura da função, para saber se estã modificando um parametro ou retornando um novo resultado;

É uma interrupção do racioocínio;

É melhor a função mudar o estado do objeto a qual pertence;

# Separação comando-consulta

As funções devem fazer ou responder algo, nunca os 2;

Ou altera informações sobre um sobjeto ou retorna elas;

# Prefira exceções a retorno de códigos de erro

Códigos de erro criam estruturas aninhadas que dificultam a legibilidade do cófigo;

Lance excessões, pois nesse caso o código fica separado do código de trabamento do erro;

Coloque o tratamento de erros em funções separadas que chamam a função que provoca o erro;

Tratamento de erro é uma coisa só, logo a função deve fazer só isso;

# Evite Repetição

Repetição amontia código, e é necessário modificar em vários locais;

é a raiz de todo o mal em softwares;

Muitos princípios e práticas existem para eliminar duplicações;

# Como escrever funções como esta?

Escrevemos funções longas e complexas com muitos parametros e com vários níveis de aninhamento;

Então refinamos, refatoramos e tiramos as duplicações;

Não aplicamos desde o início;

# Conclusão

Classes são os substantivos;

As funções são os verbos;

A arte de programar é a arte do projeto da linguagem;

Programadores experientes veem sistemas como histórias a serem contadas;

Usam os recursos da linguagem de programação, para construir uma linguagme muito mais rica e expressiva para contar a história que é o programa.

As funções bem feitas ajudam a narração da história (programa)

