# Homework: Random Phrases

## Overview
In this assignment you will create a "random phrases" web application. 

The exact theme is up to you, the example below used a *Star Trek: TNG* theme.

Ideally your theme is appropriate for all ages and audiences.

To complete this assignment, you should have completed up through the 6th web app tutorial page: [6 - JavaScript Events](web-apps-6.md).

![Web Page](_images/random-phrases-2-done.jpg)

## Instructions & Requirements
1. Create a valid HTML5 page named **random-phrases.html** that has at least the following content:
    1. A header that contains as a visible title of the page
    1. A background image (it should appear *behind* something else)
    1. Your name must be somewhere on the page
    1. An area of the page that will hold dynamically created content (ie: the random phrases, and maybe more... images?)
    1. The page will use an embedded font (something from Google fonts would suffice)
    1. The page content must be legible and nicely styled, with good choices made for colors, margins and fonts
    1. The page doesn't have to be fully-responsive, but should look acceptable and be legible on both desktop and phone.
    1. The look and theme of the page is worth 50% of the assignment
1. Display theme-appropriate random phrases when the page loads (or reloads) and when a button is clicked:
    1. You will have at least 5 phrases stored in a JavaScript array
    1. When the page loads (or reloads) a random phrase from the array will be selected and displayed. You can use `Math.random()`, `Math.floor()`, and `array.length` to accomplish this. If you get stuck, look for help on the Internet. Suggestion, the function mentioned below could be called when the page first loads. 
    1. Additionally, create a nicely styled &lt;button> and put it on the screen. Feel free to search the web for appropriate button CSS styles.
    1. Add CSS button rules for `:hover` and :`active` so that the button has a nice "over" and "down" look.
    1. Clicking the button will call a function named `displayQuote`, which will generate and display a random quote.
    1. The functionality of the page is worth 50% of the assignment

## Submission
- Post to your web site and (if desired) link to it from your 235 Home Page.  (There's lots of your own creative work here)
- Also Zip and upload to the Assignment Dropbox in myCourses.
- Tip: The coding of this shouldn't take too long, but the page layout and styling probably will.
