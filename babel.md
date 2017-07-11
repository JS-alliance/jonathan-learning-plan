Babel
=====

Insall babel globally to use in all of your projects.

    npm install -g babel
Transpile a file from ES6 to ES5:

    babel script.js --out-file src/js/script.js

Use babel to transpile ECMAscript 6 to ECMAscript 5 for browser compatibility.

Watch file and generate a transpiled file when file is updated:

    babel script.js --watch --out-file src/js/script.js

Run scripts which use es6 using babel from command line:

    babel-node script.js