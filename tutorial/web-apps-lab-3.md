# Web Apps Lab 3

Here is your starter code:

### web-apps-lab-3.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Web Apps-4-HW</title>
	<style>
		body{border:1px solid gray;}
	</style>
</head>
<body>
<h1>My Favorites</h1>
<h2>My Favorite Colors</h2>

<ol id="colorsList">
	
</ol>

<h2>My Favorite Foods</h2>

<ol id="foodsList">
	
</ol>

<h2>My Favorite Links</h2>

<ol id="linksList">
	
</ol>

<script>
"use strict";
let colors = ["red","green","blue","purple","pink"];
let foods = []; // add some foods

// Optional - can you figure out how to pull both the key AND the value
// from the `links` object literal?
let links = {
		"RIT": "http://www.rit.edu",
		"RWAG" : "https://www.facebook.com/RWAGclub",
		"New Media Club" : "http://newmediaclub.cias.rit.edu"
	}

</script>
</body>
</html>
```

### Instructions
1. Create the **web-apps-lab-3.html** file
1. Add your favorite colors and foods to the arrays. If you would rather change the theme of the page to movies, music, books or similar, feel free.
1. Write code that loops through the `colors` array, generates list items, and appends them to the appropriate list element. For this array use a classic `for` loop.
1. Write code that loops through the `foods` array, generates list items, and appends them to the appropriate list element. For this array use an ES6 `for...of` loop.
1. Be sure that your code uses `document.createElement()` to create each element.
1. Optional: add your favorite web sites to the `links` object literal, and then loop through the object, pulling out both the *key* and the *value*, generate functioning links, and add them to the last &lt;ol> on the page. The JavaScript `for...in` loop will get the job done.

### Final Result

**It should look like this, except with your favorites (whatever they are):**

![Web Page](_images/more-dom-5.jpg)

<hr>

Save the resulting file (web-apps-lab-3.html) for future submission.


