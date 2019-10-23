## XI. <a id="section11"></a>Review Exercise
Make a copy of **dom-4.html** and name it **web-apps-3-HW.html**. Delete all of the existing JavaScript code, and add JavaScript that does the following (search the web for documentation if you don't know how to do these). Make sure that you DO NOT modify the HTML source of the page in ANY way (by adding `class` or `id` attributes to the paragraphs, for example.

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
9. Change the `.innerHTML` of the &lt;footer> copyright notice to show the current year and your name

**Here is a completed example:**

![Web Page](_images/dom-9.jpg)
