# Web Apps Lab 1

Start with this code:  (It's from Web Apps, Chapter 2)

### hello-4.html (rename me to web-apps-lab-1.html)
```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="utf-8" />
   <title>Hello-4</title>
   <script>
     "use strict";
     // 1) Common JS Objects
     let colors = ["red", "green", "blue"]; // Array literal
     let person = {name:"Fred", age:20};   // Object literal
     let month = new Date().getMonth(); 
     let age = Math.round(20.999);
     let age2 = Math.floor(20.999);

     // add your new code here.
      
</script>
</head>
<body>
</body>
</html>
```

Above is a copy of **hello-4.html** from Web Apps Tutorial, Chapter 2 with all of the existing `console.log()` calls and other irrelevant code removed.

Add JavaScript that does the following (search the web for documentation as necessary):

1. Use a method of the `Array` object to append another color to the end of the `colors` array.
1. Print out the last element in the `colors` array, without hard-coding the index value.
1. Loop through the `colors` array using a `for` loop and print out each value to the console.
1. Add a new property named `school` to the `person` object and give it a value of "RIT". Then print this value to the console.
1. Print out the number of seconds that have passed since 1970 - use the `Date` object.
1. Print out the value of pi - use the `Math` object.
1. Print out the absolute value of -999 - use the `Math` object.
1. Print out an "all caps" version of the string "Hello" - use a method of the `String` object.

Save the resulting file (web-apps-lab-1.html) for future submission.
