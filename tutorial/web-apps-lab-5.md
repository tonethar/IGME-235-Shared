# Web Apps Lab 5

## A) Overview of *Color Chooser*


### 1) The starting code looks like this:

Create the following file, and name it **web-apps-lab-5.html**

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Web Apps-5</title>
	<style>
		body{
			font-family:sans-serif;
		}
		#colorform{
			background-color:#dfecdf;
			color: #111;
			padding:1em;width:400px;
		}
		#colorform p#info{
			background-color:white;
			color: black;
			width:300px;
			height:100px;
			padding:.5em;
		}
		
		#colorform legend{ 
			font-weight:bold;
			font-size:1.2em;
		}
	</style>
</head>
<body>

<div id="colorform">
	<legend>Choose your favorite color!</legend>
	<p><input type="radio" name="colorGroup" id="colorGroupRed" value="red" /> Red</p>
	<p><input type="radio" name="colorGroup" id="colorGroupGreen" value="green" /> Green</p>
	<p><input type="radio" name="colorGroup" id="colorGroupBlue" value="blue" /> Blue</p>
	<p><button id="colorButton" type="button">Submit</button></p>
	<p id="info"></p>
</div>

<script>
/* Write your code here! */
</script>
</body>
</html>
```

### 2) Which looks like this in the browser:

Note that because we `name` all of the radio buttons the same, they are considered a "group" by the browser, and we can only select one radio button at a time. Try it. The submit button currently does nothing.

![Web Page](_images/events-10.jpg)

### 3) After you have written all of your JavaScript code, and clicked a radio button ...

You should see a message indicating what color you have selected.

![Web Page](_images/events-11.jpg)


### 4) Once you click the Submit button ...

You should see another message about the color you selected, and the &lt;legend> element should also change to that color.

![Web Page](_images/events-12.jpg)

## B) Use these hints as you build the color chooser. 
1. You can use event handlers OR event listeners, it's your choice
1. You can use standard functions OR arrow functions, it's your choice
1. The **Submit button** code should be triggered by the `click` event
1. The **Radio button** code should be triggered by the `change` event
1. `document.querySelectorAll()` can be used to get reference to all of the radio buttons. You can then loop through the list you get back (use a [`for`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) or [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) loop).
	- Hint: Look up "CSS attribute selector" to find how to select multiple elements with the same attribute (your radio buttons all share a name attribute of "colorGroup")
1. To get the value of the selected radio button, use `e.target.value`
1. In the submit button code, you can check to see which radio button is selected by checking its `.checked` property
1. The `value` of these radio buttons happens to be a CSS color keyword, so it will be pretty easy to assign the value to the color property of the &lt;legend> element (and CSS color values are not case sensitive, so don't worry about the capitalization).

## C) Submission
Save a copy of what you get done for future submission as usual.

See the Weekly Checklist for submission instructions.

## D) Optional Extra Credit (worth 1 full HW)
Can you do a version of this web app, but with HTML checkboxes? Name the file **web-apps-5-with-checkboxes.html**

Hint: Checkboxes have a `.checked` property.

Hint: Don't worry about changing the color of the &lt;legend> in this version.

Checkboxes allow the user to make multiple selections. Yours should work like the version below.

**Check multiple select boxes:**

![Web Page](_images/events-13.jpg)

**Click Submit button:**

![Web Page](_images/events-14.jpg)

**Extra Credit Submission: Post to "Web Apps Lab 5 Extra Credit" dropbox**

<hr>
