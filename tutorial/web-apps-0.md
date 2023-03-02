# About this Web App Tutorial Series
## I. Overview <a id="section1"></a>
This series of tutorials & notes will get you started in creating web applications, which are *client-server* applications in which the client code runs in a web browser. 

## II. Prerequisite knowledge <a id="section2"></a>
- The HTML/CSS which we have covered in this course and in IGME-110
- CSS selectors (in particular the [CSS3 selectors](https://www.w3.org/TR/css3-selectors/#selectors)) will come in handy
- Fundamental programming concepts that you gleaned from the (at least) 2 programming classes you have taken prior to this course.

## III. How to get the most out of these tutorials <a id="section3"></a>
- Try out the code samples! Tweak and modify them! Most of the code samples are 100% complete. You just need to copy the code and paste it into a text file, and save it to your desktop. You can then make changes to the code and preview them in a web browser (we will be using Chrome)
- Be sure to complete the related Study Quiz questions for each section, and do the exercises... some will be assigned in class, others will be assigned as homework.

## IV. The Tutorials <a id="section4"></a>
1. [Introduction to Web Applications](./web-apps-1.md):
    1. what is a web app?
    1. what components of the web browser can I program?
    1. what are web standards?
1. [Introduction to JavaScript](./web-apps-2.md)
    1. a brief history of JavaScript
    1. variables, constants, and "primitive" types
    1. running code in the JavaScript console
    1. viewing error messages in the JavaScript console
    1. common built-in JavaScript objects
    1. type conversion and Falsy/Truthy values
    1. JavaScript's strict mode
1. [Introduction to the Web Browser DOM](./web-apps-3.md)
    1. did the HTML elements on the page load?
    1. selecting elements on a web page
    1. modifying elements on a web page
    1. add elements to a page, primarily with `.innerHTML`
    1. viewing the "live" DOM tree with the web inspector
    1. using the JavaScript debugger to "break on exceptions"
    1. adding code breakpoints in the JavaScript debugger
    1. viewing the value of variables in the JavaScript debugger
    1. dealing with `null` values
1. [More Web Browser DOM Methods](./web-apps-4.md)
    1. the DOM inverted tree
    1. relationships: parent, child & sibling
    1. creating and modifying DOM elements
    1. inserting and deleting DOM elements from the DOM tree
1. [JavaScript Functions](./web-apps-5.md)
    1. writing basic functions
    1. function declarations & expressions
    1. functions as *first-class* objects
    1. ES6 Block & Script Scope
    1. Variable "hoisting" and the "Temporal Dead Zone"
    1. ES6 Arrow Functions
    1. more practice with the debugger
1. [JavaScript Events & the `this` keyword](./web-apps-6.md)
    1. event handlers
    1. utilizing function declarations, expressions, and arrow functions
    1. `addEventListener()`, `removeEventListener()`
    1. adding properties to elements with `element.dataset`
    1. values of `this` in regular functions and arrow functions
    1. the `window.onload` event
1. [JavaScript Object Literals](./web-apps-7.md)
    1. creating Object literals with properties and methods
    1. iterating over object keys and values
    1. creating "Object Factories"
    1. ES6 Object literal changes
    1. value types & reference types
    1. another look at `const`
    1. controlling object mutability with `Object.seal()` and `Object.freeze()`
1. [JavaScript Arrays and array-like objects](./web-apps-8.md)
    1. methods of `Array`
    1. looping through `Array` - `for`, `for...of`, `.forEach()`, `.filter()`, `.map()`
    1. `NodeList`
    1. JavaScript typed arrays
    1. method chaining & fluent interfaces
1. [The WebStorage API](./web-apps-9.md)
    1. `localStorage.setItem(key,value)`
    1. `localStorage.getItem(key)`
    1. serializing (stringifying) objects for storage 
1. [Intro to Web Services](./web-apps-10.md)
    1. AJAX v. Ajax
    1. JSON
    1. Utilizing `XMLHttpRequest` (XHR)

## V. Assignments <a id="section5"></a>

Be sure to consult the checklists for information about what you should be doing when.

Required Homeworks will be added to this list:
- [Random Phrases 1](./HW-wa-random-phrases-1.md)
- [Random Phrases 2](./HW-wa-random-phrases-2.md)
- [Image Gallery](./HW-wa-image-gallery.md)

Optional Homeworks for extra credit are in this list:
- [Magnetic Poetry\*](./HW-magnetic-poetry.md) 
- [Pixel Artist\*](./HW-pixel-artist.md)
- [Conway's Game of Life](./HW-life.md) - animation by utilizing `window.requestAnimationFrame()` and a game loop.

Assignment at end of Chapter 10:  
- ["GIF Finder" Web Service App -- for Fall 2020](./HW-gif-finder-lab.md)

\* the starred assignments are "walkthroughs", you just have to type the code in. Take your time and be sure you understand everything, if you don't, then be sure to ask in class!

## VI. Demos <a id="section6"></a>
These demos could be nice starting points for a project:
- [Adventure!](HW-adventure.md) - keyboard control and playing an audio effect sound.
- [Chibi Card Matching Game](HW-chibi-matching.md) - 3D CSS tranforms and transitions.
- [Conway's Game of Life](./HW-life.md) - animation by utilizing `window.requestAnimationFrame()` and a game loop.
- [Web Service App - Examples & Starters](./web-service-app-starters.md)

## VII. What has been left out of this series <a id="section7"></a>
This course's content is primarily focused on giving students an introduction to web publishing, and an introduction to scripting a web browser for both applications and games. Later courses will go deeper and cover more topics, and there is very much more that that to learn about web applications on your own. Here are some major topics that we are NOT covering:

- **Advanced JavaScript Concepts** will continue to be covered in downstream courses.
- **Canvas API** is covered in [IGME-330](https://github.com/tonethar/IGME-330-Master).
- **Cloud Computing** is the practice of using a network of **remote servers** hosted on the Internet to store, manage, and process data. 
While we are going to utilize Internet resources in the form of web services, in this course our application code will be 100% on the client machine (the web browser). 
In later courses (IGME-330 & IGME-430) you will get the opportunity to read/write data to "the cloud", and even have application logic running on remote servers.
- **Database/Data Modeling** - creating a key:value server utilizing Node.js is covered in IGME-430 (an elective), *Data Modeling* and the SQL language are covered in ISTE-230 (an elective)
- **Package Managers** - such npm & Bower and other build tools such as Gulp & Grunt are covered in later courses.
- **Server-side programming** - is covered primarily in IGME-430, but we did already give you a little bit of PHP --> [About this PHP Tutorial Series](./php-0.md)
- **Web MVC or MVVM Frameworks** - these involve *data binding* and *components* examples include Vue, React and Angular, which are covered in later courses.
- **Web Games** will be covered later in this course, and we will build several games or interactive experiences using the PixiJS rendering engine. Our course's PixiJS materials can be found here --> [PixiJS Tutorial Series](./pixi-js-0.md)
- **WebGL** is an implementation of OpenGL ES 2.0 that runs natively in web browsers, and is the fastest way to draw to the browser screen. WebGL shaders may be briefly looked at while we are covering PixiJS.

## VIII. Resources <a id="section8"></a>
- http://exploringjs.com/es6/index.html
- https://developer.mozilla.org
- http://diveintohtml5.info
- http://javascript.info

<hr>

**[Get Started -> Introduction to Web Applications (chapter 1)](web-apps-1.md)**

