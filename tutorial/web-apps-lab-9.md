# Web Apps Lab 9

Start from this code (name it web-apps-lab-9.html):

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Web Storage Example</title>
</head>
<body>

<div>
What is your name -> <input type='text' id='nameField'>
</div>

<div>
What is your favorite color -> 
<select id="colorSelect">
	<option value="red">Red</option>
	<option value="green">Green</option>
	<option value="blue">Blue</option>
	<option value="magenta">Magenta</option>
	<option value="cyan">Cyan</option>
	<option value="white">White</option>
	<option value="gray">Gray</option>
</select>
</div>

</body>
<script>

/* This stuff happens "onload" */
// declare some constants
const nameField = document.querySelector("#nameField");
const colorSelect = document.querySelector("#colorSelect");
const prefix = "abc1234-"; // change 'abc1234' to your banjo id
const nameKey = prefix + "name"
const colorKey = prefix + "color";

// grab the stored data, will return `null` if the user has never been to this page
const storedName = localStorage.getItem(nameKey);
const storedColor = localStorage.getItem(colorKey);

// if we find a previously set name value, display it
if (storedName){
	nameField.value = storedName;
}else{
	nameField.value = "Turbo"; // a default value if `nameField` is not found
}

// if we find a previously set color value, display it
if (storedColor){
	colorSelect.querySelector(`option[value='${storedColor}']`).selected = true;
}

/* This stuff happens later when the user does something */
// when the user changes their favorites, update localStorage
nameField.onchange = e=>{ localStorage.setItem(nameKey, e.target.value); };
colorSelect.onchange = e=>{ localStorage.setItem(colorKey, e.target.value); };


</script>
</html>
```

- Modify the code so that the user's color choice will also be reflected in the background color of the entire page. Conveniently, all of the color names in the &lt;select> are also CSS color keywords.
- This effect will happen both when user makes a choice in the &lt;select>, and when the user later returns to the page.
- Hint: This will only require two lines of code to get working.

**Which should look something like this:**

![Web Page](_images/web-storage-2.jpg)

Submit in the usual manner.  There is an assignment dropbox for only this exercise. 

(The next exercise -- after this one -- will be submitted as a Homework after the lab is completed)
