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
