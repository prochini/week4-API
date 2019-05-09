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
### node hw2.js list // 印出前二十本書的 id 與書名
### node hw2.js read 1 // 輸出 id 為 1 的書籍資料
```js
const request = require('request');
const process = require('process');


if (process.argv[2] === 'read') {
  request(
    `https://lidemy-book-store.herokuapp.com/books/${process.argv[3]}`,
    (error, response, body) => {
      const obj = JSON.parse(body);
      console.log(obj.name);
    },
  );
} else if (process.argv[2] === 'list') {
  request.get('https://lidemy-book-store.herokuapp.com/books?_limit=20',
    (error, response, body) => {
      const obj = JSON.parse(body);
      for (let i = 0; i < 20; i += 1) {
        console.log(`${obj[i].id}  ${obj[i].name}`);
      }
    });
}


```
### node hw3.js list // 印出前二十本書的 id 與書名
### node hw3.js read 1 // 輸出 id 為 1 的書籍
### node hw3.js delete 1 // 刪除 id 為 1 的書籍
### node hw3.js create "I love coding" // 新增一本名為 I love coding 的書
### node hw3.js update 1 "new name" // 更新 id 為 1 的書名為 new name  


```js
const request = require('request');
const process = require('process');


if (process.argv[2] === 'read') {
  request.get(
    `https://lidemy-book-store.herokuapp.com/books/${process.argv[3]}`,
    (error, response, body) => {
      const obj = JSON.parse(body);
      console.log(obj.name);
    },
  );
} else if (process.argv[2] === 'list') {
  request.get('https://lidemy-book-store.herokuapp.com/books?_limit=20',
    (error, response, body) => {
      const obj = JSON.parse(body);
      for (let i = 0; i < 20; i += 1) {
        console.log(`${obj[i].id}  ${obj[i].name}`);
      }
    });
} else if (process.argv[2] === 'delete') {
  request.delete(
    `https://lidemy-book-store.herokuapp.com/books/${process.argv[3]}`,

  );
} else if (process.argv[2] === 'create') {
  request.post(
    'https://lidemy-book-store.herokuapp.com/books', {
      form: {
        name: process.argv[3],

      },
    },
  );
} else if (process.argv[2] === 'update') {
  request.patch(
    `https://lidemy-book-store.herokuapp.com/books/${process.argv[3]}`, {
      form: {
        name: process.argv[4],
      },
    },
  );
}

```

### `process.argv` is a list of the parameters you append to the terminal command.

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
