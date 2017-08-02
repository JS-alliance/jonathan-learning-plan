	function add (x, y) {
	  return x + y
	}

	function setMultiplier (y) {
	  return x => add(x, 0) * y;
	}

	var double = setMultiplier(2);

	console.dir(double);



`console.dir(double);`


	function add (x, y) {
		  return x + y
		}

		function setMultiplier (y) {
		  return x => add(x, 0) * y;
		}

		var double = setMultiplier(2);

		console.dir(double);