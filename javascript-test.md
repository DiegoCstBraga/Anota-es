# Testes

## TDD (Test Driven Development)

Consiste em desenvolver o teste antes do código ser criado, testando e refatorando em pequenos ciclos

Etapas

+ Escrita do Teste
+ Escrita do Código
+ Refatoração

Vantagens

+ Feedback rápido
+ Maior segurança em alteração e novas funcionalidades
+ Código mais limpo
+ Produtividade

## BDD (Behavior Driven Development)

Juntar regra de negócio com linguagem de programação

Pilares

+ Testes
+ Documentação
+ Exemplos

Vantagens

+ Compartilhamento de conhecimento
+ Documentação dinâmica
+ Visão do todo

## Ferramentas de Teste

### Mocha

Instalar a dependência como desenvolvedor

```bash
npm install --save-dev mocha
```

Alterar o arquivo `package.json`, onde será alterado a parte de `scripts` para `"test": "moca"`

Criar um diretório `Teste` onde serão colocados os arquivos de teste, seguindo o padrão `fileName.spec.js`

Exemplo de Código

```js
const assert = require("assert")
const Math = require("../src/math.js")

let value = 0 

// describe -> descrever para que é o teste
describe("Math Class", function(){
  // hook
  beforeEach(function(){
    value = 0 
  })

  // recomenda-se o uso de function() para poder utilizar this.
  // it -> resultado esperado do teste, como se fosse um passo
  it('Sum two numbers', function(){
    const math = new Math()
    value = 5
    assert.equal(math.sum(value ,5), 10)
  }
  // it.only -> serve para executar apenas aquele teste
  // it.skip -> serve para pular o teste especificado
  it.only('Multiply two numbers', function(){
    const math = new Math()
    // aqui value será 0, por causa do hook
    assert.equal(math.multiply(value,5),0)
  })
})
```

[Saber mais sobre o Mocha](https://mochajs.org/)

### Chai

Serve para substituir o "assert" do node, agora sendo mais descritiva

Instalar a biblioteca como desenvolvedor

```bash
npm install --save-dev chai
```

Exemplo de Código

```js
const assert = require("assert")
const Math = require("../src/math.js")

// importando a lib Chai
const expect = require('chai').expect

let value = 0 

// describe -> descrever para que é o teste
describe("Math Class", function(){
  // hook
  beforeEach(function(){
    value = 0 
  })

  // recomenda-se o uso de function() para poder utilizar this.
  // it -> resultado esperado do teste, como se fosse um passo
  it('Sum two numbers', function(){
    const math = new Math()
    value = 5
    expect(math.sum(value,5)).to.equal.(10)
  }
  // it.only -> serve para executar apenas aquele teste
  // it.skip -> serve para pular o teste especificado
  it('Multiply two numbers', function(){
    const math = new Math()
    const obj = {
      name: 'Diego Braga' 
    }

    const obj2 = {
      name: 'Diego Braga' 
    }

    // validar um objeto
    expect(obj).to.have.property('name').equal('Diego Braga')
    // valida se os objetos possuem as mesmas caracterísiticas
    expect(obj).to.deep.equal(obj2)

    // aqui value será 0, por causa do hook
    expect(math.multiply(value,5)).to.equal(0)
  })
})
```

[Saber mais sobre o chai](https://www.chaijs.com/)

### Sinon

Serve para observar se as funções foram invocadas

Instalar a biblioteca como developer

```bash
npm install --save-dev sinon
```

Exemplo de Código

```js
const assert = require("assert")
const Math = require("../src/math.js")

// importando a lib Chai
const expect = require('chai').expect

// importando a lib Sinon
const expect = require('sinon')

let value = 0 

// describe -> descrever para que é o teste
describe("Math Class", function(){
  // hook
  beforeEach(function(){
    value = 0 
  })

  // recomenda-se o uso de function() para poder utilizar this.
  // it -> resultado esperado do teste, como se fosse um passo
  it('Sum two numbers', function(){
    const math = new Math()
    value = 5
    expect(math.sum(value,5)).to.equal.(10)
  }
  // it.only -> serve para executar apenas aquele teste
  // it.skip -> serve para pular o teste especificado
  it('Multiply two numbers', function(){
    const math = new Math()
    const obj = {
      name: 'Diego Braga' 
    }
    
    const obj2 = {
      name: 'Diego Braga' 
    }

    // validar um objeto
    expect(obj).to.have.property('name').equal('Diego Braga')
    // valida se os objetos possuem as mesmas caracterísiticas
    expect(obj).to.deep.equal(obj2)

    // aqui value será 0, por causa do hook
    expect(math.multiply(value,5)).to.equal(0)
  })

  it.only('Call req with sum and index values',function(){
    const req = {}
    const res = {
      load: sinon.spy()
    }
    const math = new Math()
    
    math.printSum(req,res,5,5)

    expect(res.load.calledOnce).to.be.true
    
  })

})
```

[Saber mais sobre Sinon](https://sinonjs.org/)
