# week4-API

API 文件
Base URL: https://lidemy-book-store.herokuapp.com

###  console 列出前10本書籍的 id 以及書名。

```js
const request = require('request');

request.get('https://lidemy-book-store.herokuapp.com/books?_limit=10',
  (error, response, body) => {
    const obj = JSON.parse(body);
    for (let i = 0; i < 10; i += 1) {
      console.log(`${obj[i].id}  ${obj[i].name}`);
    }
  });
  ```
  
  
###### `process.argv` is a list of the parameters you append to the terminal command.

```js
const obj =  JSON.parse( process.argv[2] );
console.log(obj);
console.log('Hello ' + obj.name);
```

process.argv is an array containing the command line arguments. The first element will be 'node', the second element will be the name of the JavaScript file. The next elements will be any additional command line arguments.

```js
// print process.argv
process.argv.forEach(function (val, index, array) {
  console.log(index + ': ' + val);
});
```
This will generate:
```js
$ node process-2.js one two=three four
0: node
1: /Users/mjr/work/node/process-2.js
2: one
3: two=three
4: four
```
