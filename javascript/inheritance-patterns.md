# Inheritance Patterns

## Prototypal:

A great example of creating pure prototypal inheritance:

		Object.prototype.beget = function () {
		  function F() {}
		  F.prototype = this;
		  return new F();
		}
[Source](http://javascript.crockford.com/prototypal.html)

		function Npc(level, occupation) {
		  this.level = level;
		  this.occupation = occupation;
		}

Then you can create another prototype which inherits from this one:

		function Enemy(level, occupation, weapon) {
		  Npc.call(this, level, occupation);
		  this.weapon = weapon;
		  
		  this.attack = function() {
		    return "Attacks with " + this.weapon;
		  }
		}


Also:

Object.create(myObject);


Constructor:

var Player = Function(name) {
	this.name = name;
	this.score = 0;
}