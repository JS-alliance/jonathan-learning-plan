My Algorithms
=============

## Generate prime numbers 2 - n:

	var findPrimes = function(n) {
	  var primes = [];
	  for (let i = 2; i < n; i++) {
	    primes.push(i);
	  }
	  primes.forEach(function(prime){
	    primes = primes.filter(function(element) {
	      return (element%prime !== 0 || element === prime )
	    });
	  });
	  return primes;
	}


## Generate a range of numbers in an array:

	var range = function(min, max) {
	  var numbers = [];
	  for (let i = min; i <= max; i++) {
	    numbers.push(i);
	  }
	  return numbers;
	}

## Capitalize a word

	function capitalize(str) {
	  var ending = str.substr(1, str.length);
	  var capitalized = str.substr(0, 1).toUpperCase() + ending;
	  return capitalized;
	}

## Count the appearences of a value in an array

	array.filter( element => element === valueSearched).length

## Turn a string in to an array of letters or words

	string.split('') or string.split(' ')

You can use this to count the number of occurences of a character or pattern in the string.
If the final array length is 5, then there were 4 occurences of the `split()` characters in the array.

## When running a total from the elements of a collection...

Declare the value up front and add to the value for each iteration going through the collection.

## Finding perfect powers
You can solve this by nesting 2 loops.
 * In the first loop, the base incriments while the base^2 is less than or equal to the target number.
 * In the second loop, the exponent incriments while the base^exponent are less or equal to the target

		var isPerfectPower = function(n){
		  for(let m = 2; Math.pow( m , 2 ) <= n; m++) {
		    for(let k = 2; Math.pow(m, k) <= n; k++) {
		      if(Math.pow(m, k) === n) {
		        return [m, k];
		      }
		    }
		  }
		  return null;
		}

## Formatting Money
The following tracks money in terms of cents and never converts it to a float. This would work well in a strongly typed language using only integer values

		DollarsString = '$' + parseInt(16467/100).toString() + '.' + (16467%100).toString()

This example if better for Javascript:

		DollarsString = '$' + 16467/100

The number becomes a 'float' and then a string implicitly. (Note that it is still a number as there are no 'floats' in Javascript)



## Strings


### Methods

		.charCodeAt()

Input the index of the character you want the code from.
Uppercase codes are: 65-90
lowercase codes are: 97-122
Returns a number

When you are asked to return a final value with parts seperated by some characters, use:

		array.join()

to join the elements.



function stockList(listOfArt, listOfCat){
  if (listOfArt.length === 0 || listOfCat.length === 0) {
    return '';
  }
  var bookQuantities = listOfCat.reduce( (accum, category) => {
    accum[category] = 0;
    return accum;
  }, {});
  var finalInventory = []
  for (key in bookQuantities) {
    listOfArt.forEach(code => {
      if (code.startsWith(key)) {
        bookQuantities[key] += parseInt(code.split(' ')[1]);
      }
    });
    finalInventory.push(`(${key} : ${bookQuantities[key]})`)
  }
  return finalInventory.join(' - ');
}




Find out how many of something in an array?

Filter it and get the length

String? call an array method on it first

Find out which value appears a certain number of times?
 * Use a loop
 * filter to match each item
 * return the matched value

Translating letters to other letters?
 * Use an object or hash table to save the values. (think phoenetic alphabet)

Need to multiply gigantic numbers?
 * Pass them is as strings
 * Convert them to reversed arrays of integers
 * nest 2 loops
 * access each array place as the added index of the input strings
 * if the calculated value of an index is 2 digits, take the tens digit and add it to the index + 1 of the result array.


## Create a 2 dimentional array from an array with subarrays of n length

	function chunkArrayInGroups(arr, n) {
	  
	  return arr.reduce( (newArray, element, index) => {
	    newArray[Math.floor((index)/size)] = newArray[Math.floor((index)/size)] || [];
	    newArray[Math.floor((index)/size)].push(element);
	    return newArray;
	  }, []);
	}

	chunkArrayInGroups(["a", "b", "c", "d"], 2);

## Are all letters in one string in the other? case insensitive

	function mutation(arr) {
	  var includesAll = true;
	  arr[1].split('').map(letter => letter.toUpperCase()).forEach( function (letter) {
	    if (!includesAll || !arr[0].split('').map(letter => letter.toUpperCase()).includes(letter)) {
	      includesAll = false;
	    }
	  });
	  return includesAll;
	}

	mutation(["hello", "hey"]);

## Given an array and several additional values, remove the additional values from the array.

	//Rest operator here to take in an unknown number of additinal values.
	function destroyer(arr, ...removals) {
	  // Remove all the values
	  return arr.filter(num => !removals.includes(num));
	}

	destroyer([1, 2, 3, 1, 2, 3], 2, 3);

## Instesting a number into a sorted array

	function getIndexToIns(arr, num) {
	  // Find my place in this sorted array.
	  arr.sort( (a, b) => a - b);
	  for (var i = 0; i< arr.length; i++) {
	    if (arr[i] >= num)
	    return i;
	  }
	  return i;
	}

	getIndexToIns([3, 3, 5, 20], 5);

## Solving a cipher decoding text letter by letter

	function rot13(str) { // LBH QVQ VG!
	  return [].map.call(str, (letter) => {
	    if ( 65 <= letter.charCodeAt(0) && letter.charCodeAt(0) <= 91) {
	      if (letter.charCodeAt(0)+13 > 90) {
	         return String.fromCharCode(letter.charCodeAt(0) + 13 - 26);
	      }  
	      return String.fromCharCode(letter.charCodeAt(0)+13);
	    }
	    return letter;
	  }).join('');
	}

	// Change the inputs below to test
	rot13("SERR CVMMN!!");

## Return the rest of an array once it meets a predicate


	function dropElements(arr, func) {
	  for (let i = 0; i<arr.length; i++) {
	    if ( func(arr[i]) ) {
	      return arr.slice(i);
	    }
	  }
	  return [];
	}

	dropElements([1, 2, 3], function(n) {return n < 3; });





// groupBy takes an array and splits it into sets, grouped by the 
// result of running eac value through the predicate. If the 
// predicate is a string instead of a function, it groups by the 
// property named by predicate on each of the values. 

function groupBy(collection, predicate){ 
  return collection.reduce(function(result, item, index) {
    var key = predicate(item)
    if (!result[key]) {
      result[key] = [];
    }
    result[key].push(item);
    return result;
  }, {});
}

  // make an empty object result.
  // for every item in the collection
    // invoke the predicate on the current item,
    // if there if no key on the result object matching the return value
      // create the key and sets the value to an empty array
    // pushes the value to the array at key.
  // return the object result
    
  
var firstLetter = function(word) { return word.charAt(0); }

console.log(groupBy(['apple', 'cat', 'boat', 'card', 'bond'], firstLetter))
// returns { 'a': ['apple'], 'c': ['cat', 'card'], 'b': ['boat', 'bond'] }

// groupBy(['apple', 'cat', 'boat', 'card', 'bond'], 'length');
// returns { '5': ['apple'], '4': ['boat', 'card', 'bond'], ‘3’: [‘cat’] }
var test = groupBy([1.4, 5.6, 3.6, 1.8, 3.4], function(val) { 
  return Math.floor(val); 
});

console.log(test);

// returns { '1': [1.4, 1.8], '3': [3.4, 3.6], '5': [5.6] }



