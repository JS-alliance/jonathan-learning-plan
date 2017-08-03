jQuery
======


## Flash Cards:

### What is the jQuery syntax for an event handler that will execute when the DOM is ready?

	$(document).ready(function() {
	//...
	});


### What is the 'shortcut' method for `$(document).ready(function() {...});`?

	$(function() {...});

### How can you select items that match one selector OR another selector?

Use a comma

	$('div, article')

### How can you select only the first of a particular selector?

Use the 'first' psuedoclass

	$('div li:first')


### How can you select only the last of a particular selector?

Use the 'last' psuedoclass

	$('div li:last')


### How can you select only the odd of a particular selector?

Use the 'odd' psuedoclass

	$('#main li:odd')


### How can you select only the even of a particular selector?

Use the 'even' psuedoclass

	$('#main li:even')


### What selector will select the first, third, and fifth 'li' elements in all elements marked with the 'summary' class?

	$('.summary li:even')


### What is traversing?

Using a method to find specific DOM nodes in a jQuery object


### What is the benefit of traversing?

Traversing is faster than using complex selectors.


### Write code using traversing to find all the li elements in the #travel section

	('#travel').find('li')


### Write code using traversing to find the first div in the body

	('body div').first()


### Write code using traversing to find the last aside in the body

	('body aside').last()


### What does 'walking the DOM' refer to?

Stepping between nodes of the DOM using methods such as `.next()` and `.prev()` on a jQuery object


### Use 2 methods to select the second element of a jQuery object.

	.first().next


### What 2 methods allow you to step between siblings in a jQuery object?

`.next()` and `.prev()`


### What method allows you to (walk up the DOM) ie select the parent of the current jQuery object?

	.parent()


### What method allows you to (walk down the DOM) ie select all direct children of the current jQuery object?

	.children()


### Whats the difference between using the `.find()` and `.children()` methods?

`.children()` returns only children.
`.find()` returns all decendents.

### Select all the li elements which are children of #tours

	$("#tours").children('li')


### What is the difference between `.find()` and `.filter()`

`.find()` will search for descendants of nodes in the object while `.filter()` will search within the object and return an object containing those which match the criteria.


### What is the difference between using `.parent()` and `.parents()`?

`.parent()` returns the nearest parent. `.parents()` returns all ancestors.


### What does `.closest('.vacations')` select?

The closest ancestor which matches the parameter. In this case, the vacations class.


### What method selects all sibling nodes?

`.siblings()`


### What method selects a specific numeric index in the current node list?

`.eq()`  as in `$('li').eq(2)` selects the third list item.


### What 2 methods select all previous OR all next elements in the node list?

`.nextAll()` or `.prevAll()`


--------------------------------------------------------

DOM Manipulation


### Create a new button DOM node with the text 'Buy Now'.

	var button = $("<button>Buy Now</button>");


### What does `.prepend()` do?

Adds the element as the first child of the currently selected node.


### What does `.appepend()` do?

Adds the element as the last child of the currently selected node.


### What does `.after()` do?

Adds the element as a sibling after the currently selected node.


### What does `.before()` do?

Adds the element as a sibling before the currently selected node.


### What does `.remove()` do?

Removes the node from the DOM.


### What method removes all child elements of the current element?

`.empty()`




-------------------Not implimented-----------------------------+-+-+

### How are `.appendTo()`, `.prependTo()`, `.instertAfter()`, `.insertBefore()` different than the `.prepend()`, `.append()`, `.after()`, and `.before()`?

The first are methods used by the new node and you pass in the destination node as an argument.
The second are methods used by the destination node and you pass in the new node as an argument.


### Create a new h2 DOM node with the text 'Vacations'.

	var vacations = $("<h2>Vacations</h2>");

### Add the node stored in the variable `vacations` as the first child of the element with id #main.

	vacations.prependTo('#main'); // or...
	('#main').prepend(vacations);


### Add the node stored in the variable `footer` as the last child of the body.

	footer.appendTo('body'); // or...
	('body').append(footer);


### Add the node stored in the variable `section4` as a sibling after `#section3`.

	section4.appendTo('#section3'); // or...
	('#section3').append(section4);


### Add the node stored in the variable `section4` as a sibling after `#section3`.

	section4.insertAfter('#section3'); // or...
	('#section3').after(section4);


### Add the node stored in the variable `header` as a sibling before `#main`.

	header.insertBefore('#main'); // or...
	('#main').before(header);

--------------------------------------------------
Events 


### Add an event handler on `#buy-now` to run when it is clicked.

	$('#buy-now').on('click', function() {

		});


### How can you dynamically associate the element you are clicking with the target of methods in your event handler?

Use the `this` keyword.


### What is `this` when an event is triggered?

The element to which the handler is attached.


### What is event delegation?

When the event handler is attached to a parent element, but the event is triggered by interaction with one of its children.


### What is the context of `this` when using event delegation?

The element which triggered the event.  In jQuery, the second argument in the `.on()` method.


### create an event handler on the #intro element which is triggered whenever a 'button' is clicked.

	$('#main').on('click', 'button', function(){...})


### Why would you use event delagation instead of creating an event handler for each button?

It's more efficiant to create a single handler when the behavior is the same for many elements.


### What strings can you pass into the `.on()` functions as mouse event triggers?

'click', 'focusin', 'mousedown', 'mouseup', 'mousemove', 'mouseover', 'mouseenter', 'dblclick', focusout, 'mouseout', 'mouseleave'


### What are the 3 arguments for keyboard events? 
'keypress', 'keydown', 'keyup'


### What are the 5 main form events?
'focus', 'blur', 'select', 'submit', 'change'


### What is `.stopPropagation()` ?

It prevents the events from bubbling up to ancestor elements in the DOM and unintentionally triggering additional handlers.


### What is `.preventDefault()` ?

It prevents the default browser behaviors related to events from being execuuted.  This includes page refreshes and moving to the top of the page.


### What is the context of `this` in the following code:

	$('#main').on('click', 'button', function(){...})

The `button` which is clicked.


### What method will remove an event handler?

`.off()` as in `$('div').off('click')`


### What properties does the event object contain?

__`pageX`__, `pageY` (Mouse position)
__`type`__, 'click', 'keypress', etc...
__`which`__ The button or key that was pressed.
__`data`__ Any data that was passed in when the event was bound.
__`target`__ The DOM element which initiated the event.


------------------------------------------------------------------------------------------------

Changing element attributes
-----------------------------


### What HTML attribute on the element would be selected with the following code:

	$('flights').data('price')

The `data-price` attribute. as in `<div class='flights' data-price="400">`


### What is the HTML5 `data-` property for?

Storing custom data in an HTML element.


### What's the code to add the class 'on-sale' to the '.bahamas' elements?

	$('.bahamans').addClass('on-sale');


### What method allows you to get or set CSS properties?

`.css()`


### What does `.val()` return?

The current value in a form field.


### What can you send into the `.css()` method?

Either two strings representing the property and the value to set or a single object with key value pairs for each css property you would like to set.


### What method allows you to select any element attribute?

`.attr()` as in `$('img').attr('src')`


### What method allows you to change any element attribute?

`.attr()` as in `$('img').attr('src', 'http://www.image.com/logo.png')`


### What method is used to check if an element has a particular class assigned to it?

`.hasClass()` as in `.hasClass('selected')`


### What method allows you to get and set form field values?

`.val()`


### What 3 methods allow you to add or remove classes?

`.addClass()`, `.removeClass()`, `.toggleClass()`,


### What method allows you to remove any attribute?

`.removeAttr()` as in `.removeAttr('img', 'src')`


### What method selects or replaces content inside an element including HTML markup inside of it?

`.html()` as in `.html('#main', '<div>Content</div>')`


### What method selects or replaces text inside an element excluding HTML markup?

`.text()` as in `.text('#main', 'Content as text goes here!')`


### How do you add or remove multiple classes with `.addClass()`, `.removeClass()`, `.toggleClass()`?

Separate with spaces. As in: $('footer').addClass('darken fb shift round')


### What 6 methods can be used to get and set the height and width of an element?

`.height()` `.innerHeight()` `.outterHeight()`
`.width()` `.innerWidth()` `.outterWidth()`


### What type of value should be passed into the height and width methods to set height and width?

number. As in: `$('div').height(100)`


-------------------------------------------------------
Animations

### What are the 4 fade animation methods?

`.fadeIn()`, `.fadeOut()`, `.fadeToggle()`, `fadeTo()`


### What are the 3 slide animation methods?

`.slideUp()`, `.slideDown()`, `.slideToggle()`


### What are the 3 methods to show/hide?

`.show()`, `.hide()`, `.toggle()`


### What does `.animate()` do?

Animates the style of the element from its current state to the style passed in as an argument.


### How can you control the speed of animations?

Pass in a speed string ('slow', or 'fast') or number of milliseconds as an argument when calling the animating method.


### What is the benefit of using CSS animations rather than passing properties into the `.animate()` method?

You can keep your styles in your stylesheet and out of your javascript.


### How can you use CSS to force animation on an element when adding and removing classes on the object?

Give the element the 'transition' property.  It will force animation when the elements properties are changed.


### What 2 optional arguments can all animation methods take?

1. Speed as a string or in milliseconds.
1. A callback function which will execute when the animation finishes.


### What happens when several animations are sent to an element at once?

The animations will queue up and the animations will occur in sequence.


### What method will stop the current animation on an element?

`.stop()` as in `$('.dropdown').stop('click');`


### What arguments can be sent to the `.stop()` method?

 * `queue` The queue name to stop.
 * `clearQueue` remove all following animations from the queue? (`true` or `false`)
 * `jumpToEnd` Jump to the end style state of the animation. (`true` or `false`)


### What is the code to stop animation on elements with the 'dropdown' class, skip to the end state, and clear the animation queue? 

`$('.dropdown').stop(true, true);`




[jQuery - Animations](jQuery - Animations)

[jQuery - Attributes](https://ankiweb.net/shared/info/500083976)

[jQuery - Events](https://ankiweb.net/shared/info/545404601)

[jQuery - DOM Manipulation](https://ankiweb.net/shared/info/1386275570)

[jQuery - Selectors](https://ankiweb.net/shared/info/1312360566)

https://ankiweb.net/shared/decks/jQuery%20-



The most popular jQuery attribute methods and information.
