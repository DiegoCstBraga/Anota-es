# First steps with react

[Voltar para o início](./README.md)

Most of the commands are using **yarn package manager**, if you pretend to use **Node Package Manager** follow the tablesheet to compare de commands

| Yarn       | NPM           |
| ---------- | ------------- |
| `yarn add` | `npm install` |

## Setting up ReactJS

### Add package.json

```bash
yarn add -y
```

### Add react

```bash
yarn add react
```

### Add react dom

```bash
yarn add react-dom
```

## Setting up Babel

### Add Babel

```bash
yarn add @babel/core @babel/cli @babel/preset-env @babel/preset-react -D
```

### Create Babel config file

```bash
touch babel.config.js
```

### Convert file with Babel

> `--out-file` can be replaced with `-o`

```js
yarn babel src/index.js --out-file dist/bundle.js
```

Example of [Babel config file](https://gist.github.com/DiegoCstBraga/e01eb17e6eb895c29bcca94a30369c5b)

## Setting up webpack

### Add Webpack

```bash
yarn add webpack webpack-cli webpack-dev-server -D
```

### Create Webpack config file

```bash
touch webpack.config.js
```

### Add babel-loader

This dependency integrates **Babel** with **Webpack**

```bash
yarn add babel-loader -D
```

### Add html-webpack-plugin

```bash
yarn add html-webpack-plugin -D
```

### Add react-refresh-webpack-plugin

This dependency is used to keep the State of a variable even when the page is refreshed

```bash
yarn add -D @pmmmwh/react-refresh-webpack-plugin react-refresh
```

### Run Webpack

```bash
yarn webpack
```

Example of [Webpack config file](https://gist.github.com/DiegoCstBraga/e01eb17e6eb895c29bcca94a30369c5b)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMwNDgwNzA0MV19
-->