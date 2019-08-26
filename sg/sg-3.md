# Study Guide 3

- Instructions: Read Chapter 5 & 6 of *Learning Web Design* (5th Edition) and answer the questions below
- Due: XX/XX start of class

<hr>

## Chapter 5 - Marking Up Text
*This chapter introduces MANY elements for marking up text content. The elements we choose to markup our content with must be chosen **semantically** - which is in a way that most accurately describes the content’s meaning. If you don't like how the content looks when marked up with a particular element, then you can change that appearance in a stylesheet (which we'll be covering soon!)*

1. Paragraphs (`&lt;p>&lt;/p>`) are almost always displayed on a new line with a little bit of space above and below (this is called `display:block` in CSS), and paragraphs are allowed to contain text, images, and other *inline* elements (such as `&lt;em>`). Below, give examples of elements that paragraphs are NOT allowed to contain (this will be enforced by an HTML validator - i.e. a page with these elements will fail the validator):

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

    12A. The content of the `&lt;main>` element should be ______________
    
    12B. How many `&lt;main>` sections are allowed per document?
    
    12C. What sort of information does the `&lt;header>` element typically contain?
    
    12D. What sort of information does the `&lt;footer>` element typically contain?
    
    12E. A `&lt;section>` element contains ______________ (See the margin on page 85 of LWD for a hint)
    
    12F. An `&lt;article>` element contains ______________ (See the margin on page 85 of LWD for a hint)
    
    12G. Give 3 examples of content that could be contained in an `&lt;article>` element:
    
    12H. An `&lt;aside>` (sidebar) element identifies content that is ______________
    
    12I. A `&lt;nav>` element gives developers a semantic way to identify  ______________
    
    12J. An `&lt;address> element is intended specifically for ______________
    
13. Now the chapter returns to "inline" elements from page 88-97. You really need to read these over as there are a lot of useful elements you can usehere, but we're only going to ask you about 5 of them below:

    13A. Which element is use for *line breaks*?
    
    13B. Which element is use for *citations*?
    
    13C. Which element is use for *short quotations*?
    
    13D. Which element is use for *text that is incorrect*?
    
    13E. Which element is use for *abbreviations and acronyms*?
    
14. An important concept relating to the proper use of elements is *nesting* - which is basically that when you are closing elements, you need to *close* the most recent element that was opened. See the example on page 92. Re-write the HTML below to fix the nesting problem:

    ```html
    <strong><em>Turn your HW in on time!</strong></em>
    ```
   
15. We will be nice and not ask you to hand in exercise 5-2 on page 98, but it would be great it you looked at it for a minute and thought about the elements you would use. 

    *No answer required*

16. 


    
    
    
    





## Chapter 6 - Adding Links
*This chapter *

... 

