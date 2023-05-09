# JavaScript

## JavaScript Core

+ Linguagem de programação que roda no Navegador do usuário (front end)
  + Se você clicar em algum botão da página e aparece uma janela. Isso é JavaScript
  + Alteração do site ou aplicativo, conforme a interação do User
+ Roda também no computador (back-end)

## Onde pode ser utilizado?

+ Usa-se para criar aplicações web, mobile (React Native) e desktop (Electron)
+ Maioria dos sustes usam JavaScript
+ Linguagem obrigatório para Front End Web

## Variáveis do JavaScript

### Tipos de variáveis

+ number (4, 8.5)
  + Infinity
  + NaN
+ string ('Exemplo')
+ boolean (true false)
+ null
+ undefined
+ Symbol
+ object
  + Array
+ function

Descobrir o tipo de uma variável, usar o comando:

```javascript
typeof "Olá Mundo!"
```

Ele retorna `'string'`

## Manipulação de Dados

### Converter um tipo para outro

Objetivo | Comando | Comentário/Output
-|-|-
Converter para String | `String(20)`
Converter para String | `20.toString()`
Converter para Int | `Number.parseInt(n)`
Converter para Float | `Number.parseFloat(n)`
Converter para Número | `Number('2.2')`

---

### Manipulando String

Objetivo | Comando | Comentário/Output
-|-|-
Saber tamanho de uma String | `string.length`|
Quebrar a String por um delimitador, transforma em array | `string.split('x')`|
Substituir um valor por outro|`string.replace('nome1','nome2')`|Aceita RegEx
Pegar o último caractere de um valor|`string.slice(-1)`|
Retornar um valor exceto a última letra|`string.slice(0,-1)`|
Retornar um valor a partir da segunda letra|`string.slice(1)`|
Retornar uma quantidade n de valores a partir de uma posição|`string.substring(0,3)`|

---

### Manipulando Number

Objetivo | Comando | Comentário/Output
-|-|-
Define quantidade de casas decimais | `number.toFixed(2)`|

---

### Manipulando variáveis compostas (Arrays)

Objetivo | Comando | Comentário/Output
-|-|-
Retornar tamanho do Array|`people.length`|
Verificar se é um Array|`Array.isArray(people)`|
Iterar itens do Array|`people.forEach((value, index, array) => value)`|
Criar um Array|`let nomeArray = []`|
Criar um Array|`let nomeArray = nomeArray.Array()`|
Criar um Array a partir de um array-like ou iterable object|`let nomeArray = nomeArray2.Array()`|
Adicionar valores no final de um Array|`nomeArray.push(2)`| retorna o tamanho do array
Remover valores do final de um Array|`nomeArray.pop()`| retorna o item removido
Adicionar valores no início de um Array|`nomeArray.unshift(1)`| retorna o tamanho do array
Remover valores do início de um Array|`nomeArray.shift()`| retorna o item removido
Ordenar valores de um Array contendo String|`nomeArray.sort()`|
Ordenar valores de um Array contendo number|`arr.sort((a,b)  => a-b)`|
Concatenar arrays|`array1.concat(array2)`|
Pegar uma parte do array|`array.slice(0,2)`|
Inserir e remover elementos|`array.splice(0,0,"first")`|arr.splice(pos, qtdRemover, valor)
Conferir se um elemento existe|`arr.includes(2)`|
Conferir se um item do Array corresponde à uma condição|`arr.some(value => value % 2 === 0)`|
Conferir se todos os itens do Array correspondem à uma condição|`arr.some(value => value % 2 === 0)`|
Inverter o sentido de um Array|`arr.reverse()`|
Transformar o array em outro tipo de dado|`arr.join('-')`
Procurar por um valor dentro de um Array|`nomeArray.indexOf(valorDesejado)`|caso o valor não exista, será retornado -1
Procurar por um primeiro valor |`arr.find(value => value > 2)`|
Procurar pelo primeiro índice de um valor |`arr.findIndex(value => value > 2)`|
Retornar os índices do array|`arr.keys()`|
Retornar os valores das chaves um objeto|`arr.values()`|
Retornar um array de arrays contendo nome_prop e valor_prop|`arr.entries()`|

#### Percorrer elementos de um Array (map)

```js
const arr = [1,2,3,4,5]

arr.map(value => value * 2)
console.log(newArr)
// [2,4,6,8,10]
```

#### Filtrar elementos de um Array (filter)

```js
const arr = [1,2,3,4,5]
const allValuesGreaterThanTwo = arr.filter(value => value > 2)

console.log(allValuesGreaterThanTwo)
// [3,4,5]
```

#### Transformar um Array em outro tipo de dado (reduce)

```js
const arr = [1,2,3,4,5]

arr.reduce((acumulado, value) => acumulado += value, 0)
// acumulado => o que será retornado
// , 0 => o tipo da variável, no caso, inicia seu valor em 0
// 15
```

#### flat & flatMap

```js
// flat
const arr = [1,2,[3,4]]
let depth = 1

let newArr = arr.flat(depth)
console.log(newArr)
// [1,2,3,4]
```

```js
const arr = [1,2,3,4]

arr.flatMap(value => [value*2])
// [2,4,6,8]

arr.flatMap(value => [[value*2]])
// [[2],[4],[6],[8]]
```

---

#### Manipulando Object

```js
let user = {
  name: 'Diego',
  age: 21,
}

const person = {
  name: 'Gustavo'
}
```

Objetivo | Comando | Comentário/Output
-|-|-
Alterar a propriedade de um objeto|`user.name = 'Outro nome 1'`|
Alterar a propriedade de um objeto|`user['name'] = 'Outro nome 2'`|
Criar uma propriedade|`user.lastName = 'Braga'`|
Deletar uma propriedade|`delete user.lastName`|
Retornar as chaves do objeto|`Object.keys(user)`| ['name', 'age']
Retornar os valores das chaves um objeto|`Objetct.values(user)`| ['Diego', 21]
Retornar um array de arrays contendo nome_prop e valor_prop|`Object.entries(user)`| [['name','Diego'],['age',21]]
Fazer Merge das propriedade de um objeto|`Object.assign({}, user, {fullName: 'Diego Braga'})`|
Prevenir alterações no Objeto|`Object.freeze(user)`|
Permitir alterar apenas propriedades existentes de um objeto|`Object.seal(person)`|

#### Input e Output

```javascript
// APRESENTA UM 'POP-UP' COM A MENSAGEM
window.alert('Minha primeira mensagem')
 
// APRESENTA DUAS OPÇÕES PARA O USER ESCOLHER
window.confirm('Está gostando de JS?') 

// APRESENTAR UM INPUT PARA INSERIR ALGUM DADO
window.prompt('Qual é o seu nome?') 
```

## Definindo um valor no formato de alguma moeda

```javascript
let salario = 1554

salarioReais = salario.toLocaleString('pt-BR', {style: 'currency', currency: 'BRL'})

salarioDolar = salario.toLocaleString('pt-BR', {style: 'currency', currency: 'USD'})

salarioEuros = salario.toLocaleString('pt-BR', {style: 'currency', currency: 'EUR'})

console.log(salarioReais)
console.log(salarioDolar)
console.log(salarioEuros)
```

OUTPUT:
`R$ 1.554,50`
`US$ 1.554,50`
`€ 1.554,50`

### Template String

```javascript
let nome = 'Diego'
console.log(`O nome é ${nome}`)
```

## Lidando com erros

### throw e try...catch

```js
function checkName(name = '') {
  if (name === '') {
    throw new Error('Name is empty! Please insert a proper name')
  }
  // caso dê erro, ele para de executar a função
  console.log(name)
}

try {
  checkName()
} catch (e) {
  console.log(e) // 'Name is empty! Please insert a proper name'
}
```

## Operadores do JavaScript

### Aritméticos

+ \+ soma
+ \- subtração
+ \* multiplicação
+ \/ divisão
+ \% resto da divisão inteira
+ \** exponenciação

### Atribuição

+ = atribuição simples
+ auto-atribuição
  + n = n + 4
  + n = n - 1
  + n += 4
  + n -= 1
  + etc
+ incremento
  + x++
+ decremento
  + x\-\-

### Relacionais (resultado bool)

+ \> maior
+ \< menor
+ \>= maior ou igual
+ \<= menor ou igual
+ == igual a
+ === igualdade restrita (mesmo tipo e valor)
+ != diferente de
+ !== desigual restrito

### Lógicos (prioridade: and -> not -> or)

+ ! not (negação)
+ && and (conjunção)
+ || or (disjunção)

### Ternário

+ teste ? true : false
  
### Falsy

> Quando um valor é considerado false em contextos que um boolean é obrigatório

+ false
+ 0
+ -0
+ ""
+ null
+ undefined
+ NaN

### Truthy

> Quando um valor é considerado true em contextos que um boolean é obrigatório

+ true
+ {}
+ []
+ 1
+ 3.23
+ "0"
+ "false"
+ -1
+ Infinity
+ -Infinity

### Rest operator

+ Serve para receber N parâmetros, sendo do tipo Array

```js
const sum = (...rest) {
  return rest.reduce((acc, value) => acc + value, 0)
}

console.log(sum(1,2,3,4))
// 10
```

### Spread operator

+ Serve para distribuir N parâmetros para uma função
+ Pode receber
  + Strings
  + Arrays
  + Objetos literais-
  + Objetos iteraveis

```js
const multiply = (...args) => args.reduce((acc, value) => acc * value, 1)

const sum = (...rest) => {
  return multiply(...rest)
}

console.log(sum(1,2,3,4))
// 10
```

### Destructing Assignment

```js
// Array
let [apple, banana, orange] = ["Apple", "Banana", "Orange"]

// Object
let obj = {
  name: 'Diego'
}

// colocar o mesmo nome da propriedade
let { name } = obj

// caso queira atribuir a outro nome, colocar ":" + "nomeVar"
let { name : newName } = obj

// Function
// Aceita default values
function sum([a, b] = [0, 0]) {
  return a + b
}

console.log(sum(2))
```

### Symbols e Iterators

+ Symbol: gerar um identificador **único**
+ Well known Symbols
  + iterator
  + split
  + toString Tag

```js
// Symbol Iterator
// Percorre um array, String ou objeto, ele retornar dois valores, VALUE e DONE
// VALUE == valor inteiro
// DONE == boolean
// É possível associar com o for...of
const arr = [1,2,3,4]

const it = arr[Symbol.iterator]()

while(true){
  const [value, done] = it.next()

  if(done){
    break
  }

  console.log(value)
}
```

Usando Symbol.interator em um objeto

```js
const obj = {
  value: [1,2,3,4],
  [Symbol.iterator]() {
    let id = 0

    return {
      next: () => {
        return {
          i++
          value: this.values[i - 1],
          done: i > this.values.length
        }
      }
    }
  }
}

const it = obj[Symbol.iterator]()
```

[Mais informações sobre iterator](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Iteration_protocols)

### Generators

+ são funções com pausas e retornam valores
+ a palavra ***yield*** indica a pausa dentro da função
  + para dar continuidade bastar usar o método next()

```js
function* hello(){
  // Yield retorna dois valores, VALUE e DONE
  // VALUE == valor inteiro
  // DONE == boolean

  console.log('Hello')
  // adicionando um valor na interação
  yield 1
  
  console.log('Hello')
  const value = yield
  
  console.log(value)
}

const it = hello()

console.log(it.next())
console.log(it.next())
console.log(it.next('Outside!'))
```

[Saiba mais sobre Generator](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Generator)

### Condições

#### Condição Simples

```javascript
if(condicao == true){
  console.log(`Positivo`)
} 
```

#### Condição Composta

```javascript
if(condicao == true){
  console.log(`Positivo`)
} else {
  console.log(`Negativo`)
}
```

#### Condição Múltipla

```javascript
switch(expressão){
  case valor1:
    break
  case valor2:
    break
  case valor3:
    break
  default:
    break
}
```

## Repetições

### While

```javascript
// TESTE LÓGICO NO INÍCIO
while (true){
  fnName()
}
```

### Do...While

```javascript
// TESTE LÓGICO NO FINAL
do {
  fnName()
} while (condição)
```

### For

```javascript
for(let i = 0; i < 5; i++){
  console.log(`index [${i}]`)
}
```

### For...in

> Pega as propriedades de um objeto.
>
> Pega o index de um Array.

```javascript
let  person = {
  name: 'João',
  age: 20,
  weight: 88.6
}

for(let property in person){
  console.log(`A propriedade do objeto é ${property} `)
  console.log(`e seu valor é ${person[property]}`)
}
```

### For...of

> Pegar os valores de um array ou objeto

```javascript
let  nomeArray  = ['João','Paulo','Pedro']

for(let name of nomeArray){
  console.log(`${name} `)
}
```

## Funções

> São **ações** executadas assim que **chamadas** ou em decorrência de algum **evento**.
>
> Uma **função** pode receber **parâmetros** e retornar um **resultado**.

```javascript
// DEFININDO UM VALOR DO PARÂMETRO CASO NÃO À PASSE
function soma(n1=0, n2=0){
  return n1 + n2
}

console.log(soma(1))
// JÁ QUE NÃO FOI ATRIBUÍDO UM SEGUNDO PARÂMETRO, SEU VALOR SERÁ ZERO
```

### Arrow Function

```javascript
// Arrow Function com return implícito

const arrowFn = () => 'seu return aqui'
```

```javascript
// Arrow Function sem return implícito

const arrowFn = () => {
  // expressão qualquer
  return 'seu return aqui'
}
```

### Callbacks e Promises

> Um Callback é uma função passada como um argumento para outra função.

Promises

State | Definition
------|-----------
Pending | Em execução
Fulfilled | Executou sem erros
Rejected | Apresentou algum erro

```js
const myPromise = new Promise((resolve, reject) => {
  resolve('Your Promise is Fulfilled!')
})
```

Ação|Atributos
-|-
Retorna as Promises ao mesmo Tempo|`Promise.all([Promise1(),Promise2()])`
Retorna a Promise que terminar primeiro|`Promise.race([Promise1(),Promise2()])`

[Saiba mais sobre callbacks](https://www.w3schools.com/js/js_callback.asp)

[Saiba mais sobre Promises](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Using_promises)

### Fetch

```js
// Fetch aceita um segundo parâmentro, onde será identificado o método e o header
// Por padrão, o Fetch vem com o método GET
fetch('/data.json')
  .then(responseStream => {
    if(responseStream === 200){
      return responseStream.json()
    } else {
      throw new Error('Request error')
    }
  })
  .then(data => {
    console.log(data)
  })
  .catch(err => {
    console.log('Error: ', err)
  })
// fetch só dará erro caso seja erro de Rede
```

[Saiba mais sobre Fetch](https://www.w3schools.com/js/js_api_fetch.asp)

## Async/Await

+ Async transforma uma função em uma promise
  + Consequentemente permite usar .then e .catch
+ Await espera que outras Promises sejam resolvidas

```js
const asyncTimer = new Promise(resolve, reject) => {
  setTimeout(() => {
    resolve(12345)
  }, 1000)
}

const simpleFunction = async () => {
  const data = await asyncTimer()
  return data
}

simpleFunction()
  .then(data => {
    console.log(data)
  })
  .catch(err => {
    console.log(`Error: ${err}`)
  })
```

[Saiba mais sobre Async/Await](https://www.w3schools.com/js/js_async.asp)

### Event Emitter

+ Exclusivo do NODE

```js
const EventEmitter = require('events')

const emitter = new EventEmitter()

emitter.on('User logged', data => {
  console.log(data)
})

emmiter.emit('User logged', {user: 'Diego Braga'})
```

### Debugging

#### Console

Ação | Comando | Comentário
-----|---------|-----------
Apresentar uma mensagem|`console.log('Texto preto')`|
Apresentar uma mensagem com sinal de alerta|`console.warn('Texto amarelo com sinal de alerta')`|
Apresentar uma mensagem com sinal de erro|`console.error('Texto vermelho com sinal de erro')`|
Indicar de onde o código está sendo executado |`console.trace()`|
Iniciar agrupamento de um número N de mensagens |`console.group('Group Name')`|
Finalizar agrupamento de um número N de mensagens |`console.groupEnd('Group Name')`|
Iniciar contagem do tempo de execução|`console.time('Timer name')`|
Finalizar contagem do tempo de execução|`console.timeEnd('Timer name')`|
Gerar tabela de dados no console|`console.table(['Digital Innovation', 'Diego Braga']`
Retornar uma mensagem do console caso uma condição seja falsa|`console.assert(1 === 2, 'Error')`
Estilizar o console|`console.log('%c log estilizado', 'color: green; font-size? 20px')`
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ3NzY1MTQ4NCw2NDQ1NTQxODhdfQ==
-->