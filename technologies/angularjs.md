# Angular JS

AngularJS with components[https://app.pluralsight.com/courses/building-components-angular-1-5]

[Angular JS Basics - Treehouse](https://teamtreehouse.com/library/angularjs-basics-1x-2)

[Build MEAN app on Treehouse](https://teamtreehouse.com/library/building-a-mean-application)


Here is a
```javascript
var fetchMovies = function($http) {
  return $http.get("/movies/json")
                     .then(function(response) {
                       return response.data;
                       });
}
```
var controller = function() {
  model.@onInit = function() {
    fetchMovies($http).then(function(movies) {
      this.movies = movies;
    });

  };
};
