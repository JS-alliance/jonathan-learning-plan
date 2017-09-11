


## Week 4
### Day 1 - Intro to NodeJS


### Day 1 - Event Loop & Async Code


### Day 2 - Servers & Node



### Day 3 - Server Side Concepts


### Day 3 - Data Storage Techniques


### Day 4 - Web Historian Solution



### Day 4 - Technical Assessment Q&A


### Day 6 - Databases

Mongo:
[Mongo University - Node](https://university.mongodb.com/courses/MongoDB/M101JS/2017_August/syllabus)

## Week 5
### Day 1 - Authentication
[bcrypt](http://en.wikipedia.org/wiki/Bcrypt)  
[Salted Hash](https://en.wikipedia.org/wiki/Salt_(cryptography))  
[Student Post](https://emilydee.com/2014/05/27/hr-## Week-5-authentication-deployment-and-angular/)  
[Authentication in Express](http://www.9bitstudios.com/2013/09/express-js-authentication/)  


### Day 2 - Solution: Shortly Express


### Day 3 - Core Angular Concepts
[Intro to AngularJS](http://www.ng-newsletter.com/posts/beginner2expert-how_to_start.html)  

```javascript
//Firs tin the app.js
angular.module('shortly', [
  'shortly.services',
  'shortly.links',
  'shortly.shorten',
  'shortly.auth',
  'ngRoute',
  'ngFx',
  'ngAnimate'
])
//Following continued:
.config(function($routeProvider, $locationProvider, $httpProvider) {
  $routeProvider
    .when('/', {
      templateUrl: 'app/auth/signin.html',
      controller: 'AuthController'
    })
    .when('/signin', {
      templateUrl: 'app/auth/signin.html',
      controller: 'AuthController'
    })
    .when('/signup', {
      templateUrl: 'app/auth/signup.html',
      controller: 'AuthController',
      authenticate: false
    })
    .when('/links', {
      templateUrl: 'app/links/links.html',
      controller: 'LinksController',
      authenticate: true
    })
    .when('/shorten', {
      templateUrl: 'app/shorten/shorten.html',
      controller: 'ShortenController'
    })
    .when('/signout', {
      redirectTo: '/signin'
    })
    .otherwise({
      redirectTo: '/links'
    })
//...
//At the end of the app in app.js:
.run(function ($rootScope, $location, Auth) {
  // here inside the run phase of angular, our services and controllers
  // have just been registered and our app is ready
  // however, we want to make sure the user is authorized
  // we listen for when angular is trying to change routes
  // when it does change routes, we then look for the token in localstorage
  // and send that token to the server to see if it is a real user or hasn't expired
  // if it's not valid, we then redirect back to signin/signup
  $rootScope.$on('$routeChangeStart', function (evt, next, current) {
    if (next.$$route && next.$$route.authenticate && !Auth.isAuth()) {
    $location.path('/signin');
    }
  });
});

//...

ng-model="url"
What is ng-click="signout()"
<form class="form-inline" ng-submit="addLink()">
{{link.visits}}
<a href='{{link.base_url}}/{{link.code}}'>{{link.base_url}}/{{link.code}}</a>
$scope.username = localStorage.getItem('username');
$scope.data = {};
$scope.getLinks = function() {
    Links.fetchLinks().then(function(links) {
      $scope.data.links = links;
    });
  };
   $scope.signout = function() {
    Auth.signout();
  };
});
```

### Day 3 - Deployment Core Concepts

Minification:
Compilation
Transpiling
Testing
Linting


### Day 4 - Deployment


### Day 6 - Shortly Angular Solution


## Week 6
### Day 1 - Intro to MVP


### Day 1 - Full Stack Overview


### Day 4 - Git Branches & Merge Conflicts


### Day 2 - Group Workflow


## Week 12
### Day 7 - ES6 Generators
