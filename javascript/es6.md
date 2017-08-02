ES6
===

[Learn about es2015-2017](http://exploringjs.com/es2016-es2017/index.html)
[Essential Features of ES2015-2016](https://blog.mindorks.com/most-used-javascript-ecmascript-2015-es6-and-ecmascript-2016-es7-features-75682cd98596)
[A great summary](https://github.com/zsolt-nagy/es6-summary/blob/master/README.md)



Template strings
----------------

let
---

const
-----

object methods
--------------
We can now remove the `function` keyword from methods.

	{
		run(steps){
			"You ran ${steps} steps!"
		}
	}

Arrow functions
--------------
[Arrow functions](http://www.zsoltnagy.eu/es2015-lesson-1-arrow-functions/)

Arrow functions and 'this'. (Context binding)
-------------------------
When using an anonymous function in an object method with the keyword `this`, you can use an arrow function to maintain the scope of this:
when using a callback function in an object method, the scope of 'this' remains constant if the callback is accessed by way of an arrow function.  To maintain scope suing a standrd anonymous function, you will need to used .bind(this) when passing the callback.
	{
		method() {setInterval(meow => {
			console.log("meow. " + this.name);

			}, 1000)
		}
	}

Default Values
--------------

Tail call optimization
----------------------
Also called 'proper tail calls'
When your function calls another function, end it like so:

	...
	//some actions
	nextFunction()
	}

By ending with a call to the next function, the stack fram can be discarded by Javascript, saving mem and cpu and preventing reaching a stack limit.


Destructuring assignment
------------------------
The commas can destructure the array into specific index assignmets.

	var [first,,,fourth] = ['France', 'Italy', 'USA', 'Russia']

[Destructuring tutorials](http://www.zsoltnagy.eu/es2015-lesson-5-destructuring/)
[Destructuring tutorials - Answers](http://www.zsoltnagy.eu/es2015-lesson-5-destructuring-solutions/)



Also usable in objects:

	var {name, price} = {
		name: 'Jonathan',
		occupation: 'software engineer',
		price: 'priceless'
	}

Now `name = "Jonathan"` and `price = "priceless"`

Generator functions
-------------------

Class syntax
------------



String methods:
---------------

	repeat(n)

Repeats the word n number of times.
