Javascript Objects
==================


## Methods
### Object.assign(target, source)
 * Returns the target object with all of the source properties having repalced all of the target properties.
 * This is a shallow copy.

		var obj1 = {name:'Paul', age:22};
		var obj2 = Object.assign({}, obj1);

		Object.assign(target, source)