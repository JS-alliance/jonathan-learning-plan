ES6
===

[Learn about es2015-2017](http://exploringjs.com/es2016-es2017/index.html)
[Essential Features of ES2015-2016](https://blog.mindorks.com/most-used-javascript-ecmascript-2015-es6-and-ecmascript-2016-es7-features-75682cd98596)
[A great summary](https://github.com/zsolt-nagy/es6-summary/blob/master/README.md)

---

## Transpiling
You can transpile it:

Turning one language into another.
Babel will transpile ES6 to ES5.

When would you use a transpiler.


----------------

## Template strings
### Template literals
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)


`string text`

`string text line 1
 string text line 2`

`string text ${expression} string text`

tag `string text ${expression} string text`


console.log('string text line 1\n' +
'string text line 2');
// "string text line 1
// string text line 2"
To get the same effect with multi-line strings, you can now write:

console.log(`string text line 1
string text line 2`);
// "string text line 1
// string text line 2"



Expression interpolation
In order to embed expressions within normal strings, you would use the following syntax:

var a = 5;
var b = 10;
console.log('Fifteen is ' + (a + b) + ' and\nnot ' + (2 * a + b) + '.');
// "Fifteen is 15 and
// not 20."
Now, with template literals, you are able to make use of the syntactic sugar making substitutions like this more readable:

var a = 5;
var b = 10;
console.log(`Fifteen is ${a + b} and
not ${2 * a + b}.`);
// "Fifteen is 15 and
// not 20."


------------------------
## Destructuring

Syntac for extracting particular items out of a collection

The commas can destructure the array into specific index assignmets.

	var [first,,,fourth] = ['France', 'Italy', 'USA', 'Russia']

first ===

in objects:
Your property name must be the same as the variable name:
`({a, b} = {a: 10, b: 20});`

Variable swapping:
```javascript
var a = 1;
var b = 3;
[a, b] = [b, a];
```

[Destructuring tutorials](http://www.zsoltnagy.eu/es2015-lesson-5-destructuring/)
[Destructuring tutorials - Answers](http://www.zsoltnagy.eu/es2015-lesson-5-destructuring-solutions/)



Also usable in objects:

	var {name, price} = {
		name: 'Jonathan',
		occupation: 'software engineer',
		price: 'priceless'
	}

Now `name = "Jonathan"` and `price = "priceless"`

---

## Spread Operator

For function calls:

myFunction(...iterableObj);
For array literals:

[...iterableObj, 4, 5, 6];


function myFunction(v, w, x, y, z) { }
var args = [0, 1];
myFunction(-1, ...args, 2, ...[3]);

var dateFields = [1970, 0, 1];  // 1 Jan 1970
var d = new Date(...dateFields);


---
## Rest Operator


---  
## Default Values

function [name]([param1[ = defaultValue1 ][, ..., paramN[ = defaultValueN ]]]) {
   statements
}

function multiply(a, b = 1) {
  return a * b;
}

function test(num = 1) {
  console.log(typeof num);
}

To force the use of default value, call the function and pass in `undefined` for that argument.

---  
## let
Block scoped

-----  
## const

Block scoped
If you want permanent assignment



---  
## object methods

We can now remove the `function` keyword from methods.

	{
		run(steps){
			"You ran ${steps} steps!"
		}
	}

---
## Arrow functions

[Arrow functions](http://www.zsoltnagy.eu/es2015-lesson-1-arrow-functions/)

(param1, param2, …, paramN) => { statements }
(param1, param2, …, paramN) => expression
// equivalent to: (param1, param2, …, paramN) => { return expression; }

// Parentheses are optional when there's only one parameter name:
(singleParam) => { statements }
singleParam => { statements }

// A function with no parameters should be written with a pair of parentheses.
() => { statements }

### Advanced Syntax
// Parenthesize the body of function to return an object literal expression:
params => ({foo: bar})

// Rest parameters and default parameters are supported
(param1, param2, ...rest) => { statements }
(param1 = defaultValue1, param2, …, paramN = defaultValueN) => { statements }

// Destructuring within the parameter list is also supported
let f = ([a, b] = [1, 2], {x: c} = {x: a + b}) => a + b + c;
f();  
// 6


### Arrow functions and 'this'. (Context binding)

#### No binding of this

Binding comes from where it was WRITTEN rather than where it was EXECUTED.

When using an anonymous function in an object method with the keyword `this`, you can use an arrow function to maintain the scope of this:
when using a callback function in an object method, the scope of 'this' remains constant if the callback is accessed by way of an arrow function.  To maintain scope suing a standrd anonymous function, you will need to used .bind(this) when passing the callback.
	{
		method() {setInterval(meow => {
			console.log("meow. " + this.name);

			}, 1000)
		}
	}

---  
## for ... of loop

[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
A ubiquius iterator.
Used for sets and maps...



---  
## Tail call optimization
----------------------
Also called 'proper tail calls'
When your function calls another function, end it like so:


	//some actions
	nextFunction()
	}

By ending with a call to the next function, the stack fram can be discarded by Javascript, saving mem and cpu and preventing reaching a stack limit.

---  
Set


---  
Map


---  
Generator functions

---   
Class syntax



---  
String methods:


	repeat(n)

Repeats the word n number of times.
