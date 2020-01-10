<h1>ES6 no NodeJS - Sucrase</h1>

<h3>Referências</h3>

* [Como utilizar o ES6 no Node Js, de forma simples, com o Sucrase.](https://carloslevir.com/es6-node-sucrase/)

<hr />

<strong>O que instalar em modo dev</strong>

```bash
yarn add sucrase -D
```

<hr>

<strong>No arquivo ```package.json``` adicionar:</strong>

```js
"scripts": {
  "dev": "nodemon src/server.js"
}
```

<strong>Instalar o nodemon</strong>

```bash
yarn add nodemon
```

<strong>Configrar o nodemon</strong>
* Criar arquivo na raiz ```nodemon.json````
* Adicionar ao arquivo:
```js
{
  "execMap": {
    "js": "sucrase-node"
  }
}
```

<hr />

<strong>Configurar o Debug no VS Code</strong>

* Ir no icone do inseto e clicar;
* Em configurações clicar na engrenagem;
* Criar um novo arquivo tipo node;
* Dessa forma será gerado um arquivo ```launch.json``` dentro da pasta ```.vscode/```,
* Nesse arquivo inserir o seguinte:

```js
"configurations": [
  {
    "type": "node",
    "request": "attach",
    "name": "Launch Program",
    "protocol": "inspector"
  }
]
```

* No arquivo ```package.json``` no nó ```"scripts"```, adicionar o seguinte:

```js
"debug": "node --inspect-brk -r sucrase/register src/server.js"
```

<hr />

<strong>Para executar o debug </strong>

* No terminal executar:

```bash
yarn debug
```

* No VS Code executar o debug;

* No browser iserir a url, exemplo:
```
http://localhost:3000
```



