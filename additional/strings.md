Strings
=======

## String methods

String.fromCharCode()
String.fromCodePoint()

## string.prototype methods

__Need the cahracter at the beginning?  The end?  At a specific point?__
__Does the string start with a character or end with a character?__

	String.prototype.charAt()

__Need the character code of a character at a specific index?__

	String.prototype.charCodeAt()

__ Need to add many strings together?  Add all the strings as arguments.__

	String.prototype.concat()

__Need to know if the string ends with a particular sufffix like a file extension or series of characters?__

	String.prototype.endsWith()

__Find out if a string exists in the string. Search for a string in your string.  Add an index value as the second argument to determine where to start the search.
Returns`true` or `false`__

	String.prototype.includes()

__Need to know where the first instance of a substring exists within a string? Pass in the index to start searching.  Returns the index where the substring is found.__

	String.prototype.indexOf()

__Need to know where the last instance of a substring exists within a string? Pass in the index to start searching the left side of the string.  Returns the index where the substring is found.__

	String.prototype.lastIndexOf()

__ Need to use a regular Expression and return an array of the match result?__

	String.prototype.match()

__Need to repeat a string a certain number of times?__

	String.prototype.repeat()

__Want to replace instances of a RegEx or a substring in your string? This returns a NEW string with the matching substrings replaced.__

	String.prototype.replace(regexp|substr, newSubstr|function)

__Provide a RegEx and find the index where it first appears or it will return -1.__

	String.prototype.search()

__Copy part of a string. The first argument is the start index. The second is the end index. Use negatives to start from the end.__

	String.prototype.slice()

__Turn a string into an array, seperating by whatever argument is passed.__

	String.prototype.split()

__Need to check if a string starts with a specific characters or prefix?__

	String.prototype.startsWith()

__Extract a substring by providing the start index and number of characters to include (legth of the substring)__

	String.prototype.substr()

__Extract a substring by providing the start and end index.__

	String.prototype.substring()



	String.prototype.toLowerCase()



	String.prototype.toUpperCase()


__Remove the white space before and after your string__


	String.prototype.trim()



