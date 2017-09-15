Node JS
=======

[Learn and understand NodeJS](https://www.udemy.com/understand-nodejs/learn/v4/)
[Environment guide for NodeJS](https://blog.risingstack.com/terminal-guide-for-nodejs/)
Excellent [Index of how to use Node JS inproduction](https://blog.risingstack.com/tag/node-js-at-scale/)
[How to get Nod TDD right](https://blog.risingstack.com/getting-node-js-testing-and-tdd-right-node-js-at-scale/)
[Intro to NodeJS - Videos - Sitepoint](https://www.sitepoint.com/premium/courses/node-js-an-introduction-2866)]
[How the module system works](http://fredkschott.com/post/2014/06/require-and-the-module-system/)
[How the module sytem and commonJS work](https://blog.risingstack.com/node-js-at-scale-module-system-commonjs-require/)
[REstful API with NOde, Express, and Mongo](https://www.linkedin.com/learning/api-design-in-node-js-using-express-and-mongo/exercise-2-solution-part-2)
[Web Scraping with NodeJS](https://codeburst.io/an-introduction-to-web-scraping-with-node-js-1045b55c63f7)
[Complete NodeJS Developer course - Videos - Udemy](https://www.udemy.com/course-dashboard-redirect/?course_id=922484)
[Google voice - Node API](https://github.com/amper5and/voice.js)



[TDD in NodeJS - Videos - SitePoint](https://www.sitepoint.com/premium/courses/test-driven-development-in-node-js-2932)
[Real Time Node with Kyle Simpson - Videos - Frontend Masters](https://www.linkedin.com/learning/real-time-web-with-node-js)

## modules


## require

const http = require('http');


### https

```javascript
//a simple get request.
const https = require("https");
const request = https.get("https://teamtreehouse.com/chalkers.json", response => {
  console.log(response.statusCode);
});

https.get('https.google.com/endpoint', response => {
  //we will add the data to the body as it comes in. It comes in chunks.
  let body = '';
  reponse.on('data', data => {
    //each time a bit of data is received, it will be turned to its string form and added to the message body.
    body += data.toString();
  });
  response.on('end', () => {
    JSON.parse(response.data);

  });
  console.log(response.data)
});
```
are we creating different API endpoints all on one js file?
```javascript
if (request.url === '.../')
//...
if (request.url === '.../pictures')
//...
```

### errors

```javascript
request.on('error', error => console.error(error.message));
```

### try / catch
```javascript
response.on('end', () => {
  try {
    //... Do something...
  } catch (error) {
    console.error(error.message);
  }
})

//Make a function to handle and print errors
var printError = function(error) {
  console.error(error.message);
}


```

#### Status codes
```javascript
response.statusCode


//this will make a phrase from the error 404 will instead return 'not found'
http.STATUS_CODES(response.statusCode)


```


200: OK
201: Post success

301: API endpoint Moved permanently
404: Not found
500: Internal server error
