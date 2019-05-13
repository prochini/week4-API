```js
const request = require('request');


request.get({
  url: 'https://lidemy-http-challenge.herokuapp.com/api/v3/hello',
  headers: {
    Authorization: 'Basic YWRtaW46YWRtaW4xMjM=',
    'User-Agent': 'Mozilla/5.0 (Windows; U; MSIE 6.0; Windows NT 5.1; SV1; .NET CLR 2.0.50727)',
    'X-Library-Number': 20,

  },

},
(error, response, body) => {
  console.error('error:', error); // Print the error if one occurred
  console.log('statusCode:', response && response.statusCode); // Print the response status code if a response was received
  console.log('body:', body); // Print the HTML for the Google homepage.
  console.log(response.headers['content-type']);
});
```
