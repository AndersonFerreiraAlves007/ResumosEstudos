# Meus estudos sobre Jest

```
yarn add --dev jest
yarn jest --init  
yarn add -D @types/jest
yarn add --dev eslint eslint-plugin-jest
yarn eslint --init   
```

write in package.json

```
"scripts": {
  "test": "jest --watchAll"
},
```

write in .eslintrc.json

```
{
  "env": {
    "browser": true,
    "commonjs": true,
    "es2021": true,
    "jest/globals": true
  },
  "extends": "eslint:recommended",
  "parserOptions": {
    "ecmaVersion": "latest"
  },
  "extends": ["plugin:jest/recommended"],
  "plugins": ["jest"],
  "rules": {
    "jest/no-disabled-tests": "warn",
    "jest/no-focused-tests": "error",
    "jest/no-identical-title": "error",
    "jest/prefer-to-have-length": "warn",
    "jest/valid-expect": "error"
  }
}
```

## Matchers

São métodos do objeto expect usados para testar   valores de formas diferentes. 


- .toBe(value), testa a igualdade exata, bom para os primitivos, ou referencias
- .toEqual, verifica de forma recursica cada campo do objeto ou array
- .toBeNull, verifica se é null
- .toBeUndefined, verifica se é undefined
- .toBeDefined, verifica o oposto de undefined
- .toBeTruthy, verifica qualquer resultado que o if considera como verdadeiro
- .toBeFalsy, verifica qualquer resultado que o if trata como falso

- m.toBeGreaterThan, >
- .toBeGreaterThanOrEqual, >=
- .toBeLessThan, <
- .toBeLessThanOrEqual, <=
- .toBeCloseTo, igualdade para números de ponto flutuantes, para q não ocorra erros de comparação por pequenos arredondamentos

- .toMatch, usa expressões regulares

- .toContain, verifica se o vetor ou iteral contém o item

- .toThrow, verifica se lança erro


para fazer o oposto de um matcher só colocar .not na frente


## Montagem e Desmontagem

executado antes de cada teste

```
beforeEach(() => {
  // code
});
```

executado depois de cada teste

```
afterEach(() => {
  // code
});
```

executado antes de todos os testes

```
beforeAll(() => {
  // code
});
```

executado depois de todos os testes

```
afterAll(() => {
  // code
});
```

bloco de teste

```
teste('descrption', () => {
  expect(expression).matcher()
})
```

#### escopos

```
describe('description', () => {
  // blocos de testes
})
```

```
test.only executa apenas este teste no arquivo
```

o jest executa codigos e blocos de descrição tudo na ordem que encontra, porém só executa os testes depois.

## Tests Assincronos

### Calbacks

Para testar com callbacks, deve-se passar um parametro done que deve ser chamado depois do teste

test('o dado é manteiga de amendoim', done => {
  function callback(data) {
    try {
      expect(data).toBe('manteiga de amendoim');
      done();
    } catch (error) {
      done(error);
    }
  }

  fetchData(callback);
});


### Promisses

Basta reornar a promisse no teste, e fazer o teste no bloco then

test('the data is peanut butter', () => {
  return fetchData().then(data => {
    expect(data).toBe('peanut butter');
  });
});

Quando é possivel lançar um erro, é importante usar expect.assertions(numberAssertions)

test('the fetch fails with an error', () => {
  expect.assertions(1);
  return fetchData().catch(e => expect(e).toMatch('error'));
});

test('the data is peanut butter', () => {
  return expect(fetchData()).resolves.toBe('peanut butter');
});

test('the fetch fails with an error', () => {
  return expect(fetchData()).rejects.toMatch('error');
});

### Async/Await

Obter o retorno de forma normal e fazer a verificação

test('the data is peanut butter', async () => {
  const data = await fetchData();
  expect(data).toBe('peanut butter');
});

test('the fetch fails with an error', async () => {
  expect.assertions(1);
  try {
    await fetchData();
  } catch (e) {
    expect(e).toMatch('error');
  }
});

test('the data is peanut butter', async () => {
  await expect(fetchData()).resolves.toBe('peanut butter');
});

test('the fetch fails with an error', async () => {
  await expect(fetchData()).rejects.toMatch('error');
});

## Mock

Testa links entre códigos apagando a implementação real. Captura chamadas para funções e seus parametros passados, captura instancias de construtor com new e configurações em tempo real de valores de retorno.

### Módulos

```
import fetch from 'fetch';
import Users from './users';

jest.mock('fetch');

test('should fetch users', () => {
  const users = [{name: 'Bob'}];
  const resp = {data: users};
  fetch.get.mockImplementation(() => Promise.resolve(resp))

  // or you could use the following depending on your use case:
  // axios.get.mockImplementation(() => Promise.resolve(resp))

  return Users.all().then(data => expect(data).toEqual(users));
});
```

parte do módulo

```
//test.js
import defaultExport, {bar, foo} from '../foo-bar-baz';

jest.mock('../foo-bar-baz', () => {
  const originalModule = jest.requireActual('../foo-bar-baz');

  //Mock the default export and named export 'foo'
  return {
    __esModule: true,
    ...originalModule,
    default: jest.fn(() => 'mocked baz'),
    foo: 'mocked foo',
  };
});
```

```
jest.mock('../foo'); // this happens automatically with automocking
const foo = require('../foo');

// foo is a mock function
foo.mockImplementation(() => 42);
foo();
// > 42
```

```
const myMockFn = jest
  .fn(() => 'default')
  .mockImplementationOnce(() => 'first call')
  .mockImplementationOnce(() => 'second call');

console.log(myMockFn(), myMockFn(), myMockFn(), myMockFn());
// > 'first call', 'second call', 'default', 'default'
```

```
const myObj = {
  myMethod: jest.fn().mockReturnThis(),
};

// is the same as

const otherObj = {
  myMethod: jest.fn(function () {
    return this;
  }),
};
```

### Função de simulação

mock possui propriedades de chamadas e retornos

```
const mockCallback = jest.fn(x => 42 + x);
forEach([0, 1], mockCallback);

// The mock function is called twice
expect(mockCallback.mock.calls.length).toBe(2);

// The first argument of the first call to the function was 0
expect(mockCallback.mock.calls[0][0]).toBe(0);

// The first argument of the second call to the function was 1
expect(mockCallback.mock.calls[1][0]).toBe(1);

// The return value of the first call to the function was 42
expect(mockCallback.mock.results[0].value).toBe(42);
```

```
const myMock = jest.fn();

const a = new myMock();
const b = {};
const bound = myMock.bind(b);
bound();

console.log(myMock.mock.instances);
// > [ <a>, <b> ]
```

```
const filterTestFn = jest.fn();
// Make the mock return `true` for the first call,
// and `false` for the second call
filterTestFn.mockReturnValueOnce(true).mockReturnValueOnce(false);

const result = [11, 12].filter(num => filterTestFn(num));

console.log(result);
// > [11]
console.log(filterTestFn.mock.calls[0][0]); // 11
console.log(filterTestFn.mock.calls[1][0]); // 12
```
