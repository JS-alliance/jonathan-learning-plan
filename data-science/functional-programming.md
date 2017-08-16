Functional Programming
======================

One input will always give the same output.

Functional programming is predictable.
 * Because when you use the same arguments, you get the same output each time.
Safe
 * We keep our data immutable.  We create new versions and output them.

 first class state

Modular and composable

a lambda:

You can use the arrow function syntax to create sysenct functions.


Use the rest operator:

function rest(func, ...args){

}

destructuring:

If your object takes an array of length 2 and does somthing with the valuies...
function destructure([x, y], callback) {
	return [callback(x), callback(y)];
}

PURE functions:
No side affects
doesnt mutate global state.

Allows you to replace any call to this function with the result (Memoization)

If you use global state, it can mutate.

If you affect global state, testing is morre comlicated!
You need to setup the global state and fix it later.
Requires you to mock a lot more.
Hidden sate is UNCERTAIN STATE...
It may be changing behind the scenes...


What imperitive?
 * You tell the program how to acheive a result.
 * it's a set of instructions.

What is declarative?
 * It more clearly declares what we are doing...
 * SQL is declarative...
 * HTML is declarative...

How can we apply declarative style to JS?
 * Higher order functions....
 *


Immutable state:
 * Create new state, do not mutate it...

If later in the code, you want to reference the original, it will be mutated...

Object.freeze : Cannot mutate the keys in an object.

Immutable.js:


Free your state:


How to make your state from functions rather than objects:
Rather than having an object keep track of state:
Use a function that takes some arguments and returns the object you need.
If you need to change the object later, have a function which takes in the object and applies the kind of transform you need on it.

Function operate on data and give new data.

State is NOT hidden in objects.

Always create new state.



First class functions:

Modular progrfamming using little pieces.


Parial application, currying, composing...

Closure:
createAdder = value => {
	return (y) => x+y;
}

If I am frequently using the same arguments, I can create a partial application, return a function with those arguments already supplied.

use BIND on a partial application!

use func.bind(null, ...args)  

Can a function have partial application built in?
If you pass in only SOME of the arguments, it returns a function with those applied.  When it gets enough arguments, it calls the function.

const add = x => y => x+y;
This returns a function which will take another arguement.
When the returned function is invoked, it returns the result of the x * y.

const map = fn=> array => array.map(fn);

var doAll = () => compose(func1, func2, func3);

array.map(doAll)
