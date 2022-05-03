# VueJS

[Voltar para o início](./README.md)

## O que é VueJS?

+ É um framework progressivo, ou seja, pode ser adicionado em projetos já existentes, servindo de complemento
+ Criado por Evan You (Ex-Google)em 2013/2014
+ Possui renderização declarativa
+ Trabalha com componentes
+ Possui frameworks que executam *server side rendering*
  + Nuxt.js (mais popular)
  + Gridsome
  + VuePress
+ Possui frameworks para desenvolvimento *mobile*
  + NativeScript
  + Quasar (mais promissor)
  + Vue Native

[Documentação do VueJS](https://br.vuejs.org/)

## Vue CLI

[Documentação Vue CLI](https://cli.vuejs.org/)

Instalando o Vue CLI

```bash
npm install -g @vue/cli
# OR
yarn global add @vue/cli
```

---

Criando um projeto com Vue CLI

```bash
vue create my-project
# OR
vue ui
```

## Diretivas

### v-if

+ Recebe boolean, truthy ou falsy
+ Elimina o elemento caso receba o valor `false`
+ É possível encadear *ifs*, bom para *conditional rendering*

### v-show

+ Recebe boolean
+ Melhor para esconder apenas visualmente
+ Aplica um `display: none;` na estilização da div ao receber valor `false`

### v-bind

Exemplo

```js
<a v-bind:href='url'>Site</a>
```

+ Faz com que um atributo reconheça uma variável
+ Atalho para `v-bind` é usar apenas ":" antes de um atributo

### v-for

Sintaxe

```js
<template>
  <ul>
    <li v-for='item in arr' :key='index'>{{ item }}</li>
  </ul>
</template>
```

### v-on

+ Escutar eventos

Sintaxe

```js
// sintaxe padrão
<button v-on:click='fazerAlgo'>Clique em mim</button>

// sintaxe reduzida
<button @click='fazerAlgo'>Clique em mim</button>
```

#### Eventos customizados

```js
<template>
  <li @click="$emit('fazerAlgo')">Click me</li>
</template>
```

### v-model

Sintaxe

```js
<Input v-model='text' />
```

Criando um componente para aceitar o v-model

```js
<template>
  <div>
    <h1>Input Personalizado</h1>
    <input type='text' 
      @input="$emit('input', $event.target.value)" 
      :value="value"
    />
  </div>
</template>
```

## Props

+ Normalmente a propriedade será passada como String
+ Para receber um número, array, objeto e etc, precisa usar o v-bind
+ Propriedades que são passadas mas não predefinidas são adicionadas no elemento root do componente

Chamando o componente com uma propriedade

```js
<Title nomeProp='Ola mundo' />
<Title nomeProp='Title' nomeProp2='subtitle' />
```

---

Montagem do componente

```js
<template>
  <h1>{{ nomeProp }}</h1>
</template>

// inheritAttrs = recebe boolean, define se o componente aceitará atributos
// que não estão listados, class e style sempre serão recebidos

// usar v-bind='$attrs' caso queira que o elemento filho receba
// atributos não predefinidos
<script>
  export default {
    name: 'Title',
    inheritAttrs: false,
    props: {
      nomeProp: {
        type: String,
        required: true,
      },
      nomeProp2: {
        type: String,
        required: false,
        default: 'subtext'
      }
    }
  }
</script>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE0MzYzOTIxMl19
-->