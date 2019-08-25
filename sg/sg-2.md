# Study Guide 2

- Instructions: Read Chapter 4 of *Learning Web Design* (5th Edition) and answer the questions below
- Due: XX/XX start of class

<hr>

## Chapter 4 - Creating a Simple Page
*This fairly short chapter covers how to construct a simple web page and add styles to it. Most of this should be review of concepts that we have already covered in class.*

Here are the 5 basic steps of creating a web page:

**Step #1** - Start with *content* - in this instance the content is about a fictional restaurant

**Step #2** - Give the document *structure* - you do this defining areas of the document such as the &lt;head>, &lt;body> and &lt;title>

**Step #3** - Identify text elements that you can "mark up"

**Step #4** - Add an image

**Step #5** - Change how the text looks with a style sheet

<hr>

1. Follow the instructions on pages 49-54 of LWD and create a new empty plain-text document with your preferred text editor. Name the file **index.html**

2. The text content for the page is information about the *Black Goose Bistro*, which can be found in the **LWD Chapter 4** materials in the myCourses content area. There is also an image there that you will need later on.

3. Go ahead and load the page into a browser. As you can see, all of the text is squished together.

4. Note Figure 4-8 on page 56 - this shows the document structure of a minimal web page.

5. Go ahead and mark up the document as shown on pages 58-61 and reload the page in a browser - that looks better doesn't it? Note that it doesn't look great though, because the browser is using a default stylesheet.

6. Time for some questions about the first part of this chapter that you need to answer:

    6A. Label the *opening tag*, *closing tag*, *content* and *element* of the text below:

    `<h1>Black Goose Bistro</h1>`

    6B. The *document type declaration* lets the browser know ___________

    6C. &lt;meta> elements provide ___________ - which is information about ___________

    6D. The &lt;body> element contains ___________

    6E. How many characters are in the ASCI Latin-1 character set?

    6F. How many characters are in Unicode character set?

    6G. The purpose of HTML is to add structure and ____________ to the content. It is not intended to describe how the content should *look*.

    6H. HTML markup that provides the most meaningful description of the content is called ____________ markup.

    6I. The structure of a document (the positioning and relationships among the elements) is also called the DOM, which stands for ____________

    6J. *Block* elements begin on a new ____________

    6K. Give 2 examples of *block* elements:

    6L. *Inline elements* do not ____________ they just go with the flow

    6M. Give 2 examples of *inline* elements:

7. Now go ahead and add the image to the page (recall that the image file is in mycourses) following the instructions on pages 61-65. Notice that the &lt;img> element is called an *empty* element because it does not contain any text content. Instead we must use *attributes* of &lt;img> like `src` and `alt` to tell the browser what image to display. *Attributes* are instructions that clarify or modify an element.

8. Now go ahead and style the page as shown on page 66

9. To reduce the chances of your page displaying in unexpected ways, you should validate all of your HTML documents. To validate a document is to check your markup to make sure that you have abided by all the rules of whatever version of HTML you are using. Documents that are error-free are said to be valid. 

- Go ahead and validate your **index.html** page at: https://html5.validator.nu/
- Note: Because your **index.html** document is not online, you have to use either the "File Upload" or "Text" options of the validator.

    9A. Go ahead and list out the 7 things that validators check for (on the top of page 69)
    
    
    
10. Look over the "Test Yourself" questions - the answers are in Appendix A of your book if you need to look. You DO NOT need to write the answers below.


11. Finally, add some new content to the  *Black Goose Bistro* page:
- add a new level-2 heading (i.e. an &lt;h2>) for either "Vegetarian Options" OR "Garbage Plates"
- add some supporting text (a sentence or 2) - in a paragraph - that relates to the heading you chose above
- re-validate the index.html to be sure you didn't make any mistakes
- now put the index.html file and the image into a folder named **SG-2** - ZIP this folder - and submit it to the appropriate myCourses "Assignment" (nee "Dropbox")
