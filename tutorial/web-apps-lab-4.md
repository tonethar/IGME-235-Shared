# Web Apps Lab 4

Duplicate your **web-apps-lab-3.html** file and name the copy **web-apps-lab-4.html**
Notice how the `colors` and `foods` (or whatever categories you chose) list generating code is almost the same - this violates a software development best practice known as D.R.Y. - "**D**on't **R**epeat **Y**ourself".
What you need to do is to factor out that duplicated code and put it into a function.

## Instructions

1. Hint: The function declaration looks something like this:

```javascript
function createList(listElement,array){
  // you write the rest
}
```

2. Now call this function twice, passing in a reference to the &lt;ol> element you want to populate, and the applicable array.
3. Now add a default value to the `array` parameter - an array with the values "puppydogs", "butterflies", and "lollipops". We recommend doing this the ES6 way. (These default values would only be used if no value was passed in for the array parameter)
4. Delete all the old duplicated code - now don't you feel better about yourself?
5. *Optional: now re-write `createList()` and convert it to an arrow function*

The HTML produced should be identical to what was produced in the previous version.

## Done?

Save your final version for future submission.
