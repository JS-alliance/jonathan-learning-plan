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

You can require a JSON file.

const API = require('./api.json');

const credentials = JSON.parse(API).credentials;

---

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


=============================

From Garima Batra to Everyone:  08:01 PM
i just need to be in on the gossip clearly
From Lisa Gee to Everyone:  08:02 PM
which day ?
From Peter Warner-Medley to Everyone:  08:02 PM
This is not the behviour of a winner
From james to Everyone:  08:02 PM
w000t, i'll be in/out for a bit but love leslie's talks :-D
From David Berry to Everyone:  08:03 PM
look at peter getting all sassy with the queens english
From james to Everyone:  08:03 PM
the name drew me in
From Garima Batra to Everyone:  08:03 PM
YES LESLIE
From james to Everyone:  08:04 PM
THIRSTY THURSDAY
From Lisa Gee to Everyone:  08:05 PM
Thursday and Friday
b
:D
lol
From Peter Warner-Medley to Everyone:  08:05 PM
We believe in you!
From james to Everyone:  08:05 PM
"FUCK! SHIT! Wait, this isn't live, is it?"
From Garima Batra to Everyone:  08:05 PM
hahahahahahaah that was amazing
From Christine Zimmerman to Everyone:  08:05 PM
That was funny.
From Peter Warner-Medley to Everyone:  08:06 PM
I live near an Asda!
From Lisa Gee to Everyone:  08:06 PM
i didnt know walmart was asda
From David Berry to Everyone:  08:06 PM
woooooooo
From james to Everyone:  08:08 PM
48k/s = <head_exploding>
Bribes, obviously
Why is it always mdb for solaris? wtf netflix?
hi leslie!
From chris pfaff to Everyone:  08:12 PM
dave looks like an angel
From james to Everyone:  08:17 PM
Cripes, I just came back, but know what environment variables are. A backend interview _will_ involve you talking to a sysadmin. Or, uh, what's the hipster name... "devops engineer"? :troll:
i <3 redis
From Leslie Pajuelo to Everyone:  08:18 PM
LRU-Cache
Redis
From james to Everyone:  08:24 PM
Caching is great! Other than how long to save things.
:more-subtle-troll:
Two hard things in CS: 1. Naming things; 2. Cache invalidation; 3. Off-by-one errors
Infinite memory can compensate for mostly-infinite CPU
Cluster! [censored] about systemd if you can speak linux and want to sound salty
Mark&sweep, specifically, IIRC is blocking
Yeah, but the combo is the GC thing
You have to pause it to look at what's safe to remoe
remove even
Globals are easy though, the meteor guys got the crazy recursive-closure leak
9sec?? oh ****
Yeah, that's your billions of connections
</actual-scale-problem>


===========================================



48,000 requests per second.

node performance is the most important thing for back end.
node performance.

* Make your code look more professional
* Examples of what ot talk about during interviews

* Do less. Make
 - Tell your CTO, we wont do that.
 Load balancing. - NGIX (engine x)
* GZIP - NGINX
* Node clustering is just round robin.
Static assets - NGINX (CDN)
* SSL Termination - stud (Node is not good at closing your calls) so you will do this with another service... You are doing it on anothe rpersons server.

* Mitigate
* Cache eveything...
* Environment variable* Memoize
* Memoize with L3U Cache


---

backup pressure

* When your Node server is making requests to python processes, Java, you will need to scale those up so they are not overwhelmed by Node.

---
## Circuit braker patterm

* Trips with too long timeouts


---
## Do Less - Env variable and caching

* export NODE_ENV=production (different for windows)
  * Can be set in plugins file or wherever you bootstrap your app from.
  Express, Hapi, and Koa have different handling for Environment variable..

  It caches things for you.

Server sends plain text by default.
Send GZIP from your server do the user gets a better performance.

---
## Do Less - Memoize

fucntion fibbonacci


---
## LRU cache

### lru cache
Treat it like an object.
in memory, but it can be shared. several instances of node can share it so they dont each recalculate it.
can store small images, store
Its like memoize at scale.

when can't you cache anymore?

Anything can be cachedd..
######################################### why u have to fight for

---
garbage collection is a blocking

timers?
.unref them.




## Test
apache bench will send a ton of requests





not knowing how the internet works...

fizz buzz
interview nerves are real.

Show off front end in your project.

Work in a small project where they will need youl.

Big corps have a lot of room for you to

sheppard did everyhitng again.
If you are outcomes: look at
You will get better at you area of expetice.
getting paid during job search.

## debugging
USE VSCOde
or ATOM IDE to debug NODE!!!!

Think about the code you wrote. OD NOT jump into another person's librrary.

Node8: use a console.trace.
^ learn how to use it effectively.

You are competing against applicants.

Don't have strong opinions as a newbie.

vibe that you are eager to learn/contribute.

If you present a problem, tell how you would solve it.

use stronger language.

garima: practice verbalizing the questions.
Peter: how to deal with questoins regarding tech you don't know well.

Hacker Rank is used as a screening tool. Use it.

How the internet works,

Dig in on the interview question to get a very specific question.

Follow up questions...
Get rid of variables BEFORE you start answering the question.

When leslie was on a team, the other person had created many tests. Leslie was slow.
find someone who is much better and

Everything you are doinf is systemmatic...

Someone has already solved the problem. Google it.

For your career:
be visable:
tout your own success.
Do talks to your coworkers in brown bag lunches...
If there is a problem, contemplate a solution.

Career: Be known outside of your job.
You are your own brand.
