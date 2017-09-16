

```javascript
//lets create a simple function which takes a single string as an input and runs an http request.

var getUserAvetar = function(user) {
  return new Promise(function(resolve, reject) {
    get(url, function(err, res) {
      //if there's an error, call reject(Promise supplies this method).
      if (err) {reject(error); }
      else {
        //If we got a response, then... create a variable and assign some
        var avatarUrl = res.items.property;
        resolve(avatarUrl);
      }
    });



  });
};
getUserAvetar('myUser')
.then(function(avatarURL) {
  //do some action on success
  //we can now use the avatarURL we received when the response triggered.

}).catch(function(error){
  console.error(error.message)
})

  const fs = require('fs');

  let readme = fs.readFileSync('myfile.txt' 'utf8'); // if in same directory // OR '../mtDir/myFile.txt'

  let writeFile = fs.writeFileSync('myNewFilename.txt', readMe) // filename then variable to be the text.

  ### async fs

  fs.readFile('myfile.txt' 'utf8', function(err, data) {
    // take action with the data
  });

  fs.writeFile('myNewFilename.txt', readMe, function() {

  });

//You can nest them to get one done then the next.



```
