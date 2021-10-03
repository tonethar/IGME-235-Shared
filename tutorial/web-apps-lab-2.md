# Web Apps Lab 2

Start with this code: (It's from Web Apps Tutorial Series, Chapter 3)

## dom-4.html (rename me to web-apps-lab-2.html)
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>DOM-3</title>
	<style>
		body{border:1px solid gray;}
		p b{transform: rotate(20deg)}
	</style>
</head>
<body>
<h1>My Page</h1>
<h2>Info</h2>
<h2>Pictures</h2>
<h2>More Info</h2>
<p>Blah <b>Blah</b> Blah</p>
<p>Blah <b>Blah</b> Blah</p>
<p id="lastParagraph">Blah <b>Blah</b> Blah</p>
<footer>Copyright &copy; <b>20XX</b></footer>
<script>
	"use strict"; 
  
  // add your own code here.
	
	</script>
</body>
</html>
```

Above is a copy of **dom-4.html** from Web Apps Tutorial, Chapter 3 with all of the existing JavaScript code removed.

Add JavaScript that does the following (search the web for documentation if you don't know how to do these). Make sure that you DO NOT modify the HTML source of the page in ANY way (by adding `class` or `id` attributes to the paragraphs, for example.

1. Change the `.innerHTML` of the first &lt;h1> to "My UFO Page"
1. Change the `.innerHTML` of the first &lt;h2> to "My UFO Info"
1. Change the `.innerHTML` of the 2nd &lt;h2> to "My UFO Pictures"
1. Change the `.innerHTML` of the 3rd &lt;h2> to an empty string - `""`
1. Select the &lt;body> element and make 2 style changes:
  - The `font-family` shall be "sans-serif"
  - The font `color` shall be "reddish" (specify a red shade in hexadecimal) - 
  **Power tip:** `document.body` is a handy shortcut property for getting a reference to the &lt;body> element.
6. Select the first paragraph and make some changes:
  - The inner HTML will contain the text "Report your UFO sightings here:" and have a working link to http://www.nuforc.org  - **Power tip:** In JavaScript strings, single-quotes `'` can be nested inside of double-quotes `"`
  - There will be `.style` changes:
    - the font `color` is "green"
    - the `font-weight` is "bold"
    - the `font-size` is "2em"
    - the `text-transform` is "uppercase"
    - the `text-shadow` is "3px 2px #A44"
7. Change the `.innerHTML` of the 2nd paragraph to an empty string - `""`
8. Change the `.innerHTML` of the 3rd paragraph to instead show an image of a UFO that is out on the web (use an &lt;img> tag)
9. Change the `.innerHTML` of the &lt;footer> copyright notice to show the current year and your name(s).

**Here is a completed example:**

![Web Page](_images/dom-9.jpg)

Save the resulting file (web-apps-lab-2.html) for future submission.

NOTE: See the Weekly Checklist for Submission details... The first 2 labs are due together to a folder on banjo and to the first Web App Assignment Dropbox.
