# Study Guide 3

- Instructions: Read Chapter 5 & 6 of *Learning Web Design* (5th Edition) and answer the questions below
- Due: XX/XX start of class

<hr>

## Chapter 5 - Marking Up Text
*This chapter introduces MANY elements for marking up text content. The elements we choose to markup our content with must be chosen **semantically** - which is in a way that most accurately describes the content’s meaning. If you don't like how the content looks when marked up with a particular element, then you can change that appearance in a stylesheet (which we'll be covering soon!)*

1. Paragraphs (`<p></p>`) are almost always displayed on a new line with a little bit of space above and below (this is called `display:block` in CSS), and paragraphs are allowed to contain text, images, and other *inline* elements (such as `<em>`). Below, give examples of elements that paragraphs are NOT allowed to contain (this will be enforced by an HTML validator - i.e. a page with these elements will fail the validator):

2. How many levels of heading elements are there? 

3. Which level of heading is given the most weight by search engines?

4. Which element used to be called a "horizontal rule", but it now called a "paragraph-level thematic break"?

5. Below, write the HTML necessary for an *unordered list* of the colors red, green, and blue:

6. Now do the same thing, except with an *ordered list*. You also need to add an *attribute* such that the list begins at 10 instead of at 1:

7. Note the side bars on page 77 that discuss *nested* lists, and changing the default appearance of list bullets and numbers. 

    *No answer required*

8. Which element is used to denote *long quotations*?

9. Which element preserves *whitespace* (extra spaces, tabs, line breaks, etc) and renders the content in a constant-width font?

10. If we wanted to add a caption to image, which two elements could we use?

11. Go ahead and grab **tapenade.txt** (seen on page 81) from the **LWD Chapter 4** files in mycourses, and paste the content into a new file named **tapenade.html** (see below for the starter HTML). Go ahead and mark it up with paragraphs, headings, lists, and an element that is appropriate for a long quotation. 


**tapenade.html**

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Put your title here</title>
</head>
<body>
Put your content here
</body>
</html>
```

12. Up until now, the elements we have learned have been marking up small pieces of content. Now the chapter moves on to discuss how to markup large sections of a web page. You will answer some questions about them below:

    12A. The content of the `<main>` element should be ______________
    
    12B. How many `<main>` sections are allowed per document?
    
    12C. What sort of information does the `<header>` element typically contain?
    
    12D. What sort of information does the `<footer>` element typically contain?
    
    12E. A `<section>` element contains ______________ (See the margin on page 85 of LWD for a hint)
    
    12F. An `<article>` element contains ______________ (See the margin on page 85 of LWD for a hint)
    
    12G. Give 3 examples of content that could be contained in an `&lt;article>` element:
    
    12H. An `<aside>` (sidebar) element identifies content that is ______________
    
    12I. A `<nav>` element gives developers a semantic way to identify  ______________
    
    12J. An `<address> element is intended specifically for ______________
    
13. Now the chapter returns to "inline" elements from page 88-97. You really need to read these over as there are a lot of useful elements you can use here, but we're only going to ask you about 5 of them below:

    13A. Which element is use for *line breaks*?
    
    13B. Which element is use for *citations*?
    
    13C. Which element is use for *short quotations*?
    
    13D. Which element is use for *text that is incorrect*?
    
    13E. Which element is use for *abbreviations and acronyms*?
    
14. An important concept relating to the proper use of elements is *nesting* - which is basically that when you are closing elements, you need to *close* the most *recent* element that was opened. See the example on page 92. Re-write the HTML below to fix the nesting problem:

    ```html
    <strong><em>Turn your HW in on time!</strong></em>
    ```
   
15. We will be nice and not ask you to hand in exercise 5-2 on page 98, but it would be great it you looked at it for a minute and thought about the elements you would use. 

    *No answer required*

16. What if none of the elements we’ve talked about so far accurately describes your content? HTML provides two *generic* elements that can be customized to describe your content perfectly:

    - The `<div>` element indicates a division of block content that is not otherwise defined by block elements such as `<nav>`, `<main>`, `<footer>` and so on
    - The `<span>` element indicates an inline word or phrase of text that needs markup, but there is no element matching its meaning
    - the `id` and `class` attributes are used to give `<div>` and `<span>` their meaning
    
     *No answer required*
  
17. What is the name of the `class` used in conjunction with a `<div>` on page 99 to describe a block of text and an image as a product listing? (we need to do this because there is no `<product>` element in the HTML5 specification)

18. Similarly, there is no  `<telephone>` element in HTML5. What is the name of the `class` used in conjuction with `<span>` on page 99 to describe telephone numbers? 

19. What is the difference between a `class` attribute and an `id` attribute?

20. How many elements on a page can have the same value for their `id` attribute?

21. How many elements on a page can have the same value for their `class` attribute?

22. Can an element have both an `id` and a `class`?

23. Can an element have multiple id's or multiple classes? Google it to find out.

24. Read the rest of the chapter. Be sure to check out Tables 5-2, 5-3, and 5-4. These show a lot of special characters - aka *entities* that you will very likely need to use at some point.

25. Note Exercise 5-3 - *The Black Goose Bistro News page* on Page 109 - we will be doing do a similar exercise in class so we won't require you to complete and hand in this one.

    *No answer required*

26. Go ahead and review the *Test Yourself* questions on page 111, and the Element Review on page 112. You don't need to write anything down here.

    *No answer required*
    
    
    





## Chapter 6 - Adding Links
*This chapter is shorter than the previous one, and there is a lot of great information on creating hypertext links that open other web pages, email clients, and even will dial a phone number for the user. Read on!*

1. When do you use an *Absolute URL*?

2. When do you use a *Relative URL*?

3. Write the HTML for an anchor tag that will open up the RIT home page when it is clicked. The clickable text is "RIT".

4. What do you have to do to link to a "lower" directory - for example to the couscous.html file referenced on page 119?

5. What characters do you have to use to link to a "higher" directory?

6. Stop reading on page 122. Let's write some HTML! Create a folder named **SG-3**.
    - move **tapenade.html** into the **SG-3** folder
    - create a new web page named **links.html** (use the starter HTML above)
    - give **links.html** a title - "Ima Student's Links Page" - (find the `<title`> tag in the `<head>` section) - where Ima Student is your actual name.
    - add a `<main>` element to the `<body>` element of **links.html**
    - add a level-1 heading to **links.html** that also says "Ima Student's Links Page" 
    - add an *unordered list* (use the `<ul>` element) of links to **links.html**. There will be *absolute* URL hypertext links to three imdb.com movie pages - choose movies that you enjoy or ones that you would like to see.
    - these 3 links need to open in a new browser window. Look ahead to page 127 to see how to do this.
    - add a footer to the bottom of **links.html**. In this footer add a hypertext link to **tapenade.html**  - this will be a *relative* URL.
    - Now open up **tapenade.html** and add a footer element to the bottom of it. In this footer add a link to **links.html** - this will also be a *relative* URL.
    - Test your "footer" links that link these 2 pages. You should be able to toggle back and forth between **links.html** and **tapenade.html** by clicking.
    - test your IMDB links - these should function when clicked on - and open the approriate IMDB page in a new window.
    
 7. Read the sections about linking to fragments (which is really handy!), mail links, and telephone links.
 
 8. Try answering the questions in *Test Yourself* on your own, but we aren't going to collect the answers.
 
   *No answer required*

**SUBMISSION: ZIP the SG-3 folder, and post it in the appropriate place in myCourses**.

