# Web Apps Lab 8

See the HTML comments in the starter code below for what you have to do - name this **web-apps-lab-8.html**

### web-apps-lab-8.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>web-apps-ex-8</title>
</head>
<body>
<script>
let cars = [
	{make:"Toyota",	year:2015},
	{make:"Jeep",	year:1946},
	{make:"Ford",	year:2017},
	{make:"Tesla",	year:2018},
	{make:"Fiat",	year:1982},
	{make:"Dodge",	year:1970},
	{make:"Chevy",	year:1957},
];

// For this exercise you will use Array.filter(), Array.sort(), and Array.map() on
// the cars array above.

/*
 1 - Create a new array named 'classicCars' that contains only those cars with a
 .year of 1970 or earlier. Use Array.filter() on the cars array:
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
*/


/*
 2 - Create a new array named 'sortedByYear' that contains the contents of the
 car array, sorted by .year, ascending (oldest to most recent)
 Use Array.sort() on the cars array - and read about writing a comparison function here:
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort
 
*/


/*
 3 - Create a new array named 'newerYearsOnly' that contains only the .year property 
 (not the entire car object) of those cars that are .year 2010 or newer. 
 Use Array.map() on the cars array:
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
 
 This will give you a few undefined values. Use Array.filter() to get rid of these 
 undefined values so that newerYearsOnly contains only years (Numbers)
 
 Hint: you could use Number.isInteger() or the typeof operator:
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof
 
 You could do this additional filter on a separate filter on the different lines,
 or as a "one-liner" by chaining the method calls.
*/

debugger;
</script>
</body>
</html>
```

**Which looks like this in the debugger:**

![Web Page](_images/arrays-1.jpg)

<hr>

Save your work for future submission.  See the Assignment Dropbox for instructions on how to submit your work.
