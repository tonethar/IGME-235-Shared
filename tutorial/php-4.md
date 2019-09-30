# 4 - PHP Mail & Forms

## Contents
<!--- Local Navigation --->
I. [Overview](#section1)

II. [The PHP `mail()` function](#section2)

III. [HTML Forms](#section3)

IV. [Naming the form fields](#section4)

V. [PHP code to handle the form](#section5)

VI. [Testing your form](#section6)

VII. [Styling your form](#section7)

VIII. [Homework](#section8)

<hr>

## I. <a id="section1">Overview
Today we are going to look at creating a typical HTML contact form where a user can type in a message, and then click a button to send the message, without ever having to open up their email client. To accomplish this we will need to cover a few things today:
- how to utilize PHP `mail()` function
- how HTML forms can capture user inputed information
- how data can be passed to PHP scripts

This will also come in handy later in the semester, when you will be required to add a contact form to your portfolio site.

## II. <a id="section2">The PHP `mail()` function

The PHP `mail()` function will send mail using the email program specified in our php.ini file. It's easy to use - go ahead run this code on banjo. You will need to replace `abc1234` with your RIT id.

**php-mail-1.php**
```php
<?php
	$to = "abc1234@rit.edu";
	$from = "abc1234@rit.edu";
	$subject = "Web Form";
	$message = "Hello world!";
	$headers = "From: $from" . "\r\n";

	// send the message!
	mail($to,$subject,$message,$headers);
?>
```

- Load the page (just once) and within a minute or two you should receive an email (from yourself!).
- You can get more details about the various parameters of the `mail()` function here:
    - https://www.w3schools.com/php/func_mail_mail.asp
    - http://php.net/manual/en/function.mail.php
- PS - once you are finished testing this script on banjo -  delete it -  unless you like to get tons of spam, from yourself.


## III. <a id="section3">HTML Forms
	
Now we would like to extend our first attempt by adding some way to capture a site visitor's message. HTML forms to the rescue!

The three form tags we will need are:

- &lt;form> - https://www.w3schools.com/Html/html_forms.asp
- &lt;input> - https://www.w3schools.com/Html/html_form_input_types.asp  - there are many different kinds of &lt;input> tags, be sure to check out the list.
- &lt;textarea> - https://www.w3schools.com/tags/tag_textarea.asp

**php-mail-2.php**
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Contact Us</title>
	<style>

	label {
		display:block;
		margin-top:20px;
		letter-spacing:2px;
	}
	
	#submit {
		display:block;
		margin-top:20px;
	}
	
	</style>
</head>
<body>
	<h1>get in touch</h1>
 <form method="post" action="<?php echo $_SERVER["PHP_SELF"];?>">
        
            <label>Name</label>
            <input name="name" placeholder="Type Here">
            
            <label>Email</label>
            <input name="email" type="email" placeholder="person@sample.com">
            
            <label>Message</label>
            <textarea name="message" placeholder="Type Here"></textarea>
            
            <label>*What is 2+2? (Anti-spam)</label>
            <input name="human" placeholder="Type Here">
            
            <input id="submit" name="submit" type="submit" value="Submit">
        
        </form>
        
</body>
</html>
```

 **Which gives us a serviceable (albeit unattractive) form:**
 
 ![Screenshot](_images/php-mail-1.jpg)

- One other new thing here is this line of code, which is the value of `action=`:

`<?php echo $_SERVER["PHP_SELF"];?>`

- "PHP_SELF" is the name of the current file, so by making this the value of `action`, we are assured that the form will call itself no matter what the PHP file is named.

## IV. <a id="section4">Naming the form fields
- Note that we are using the `name` attribute in our form fields. `name` will be used to identify the value of each form field when the form is submitted.
- To see this happening:
    - change the `method` of the &lt;form> from "post" to "get"
    - fill in some values and click the submit button
    - you should see something like this the browser's location box:
    
  `https://people.rit.edu/~abc1234/230/test/php-mail-2.php?name=Fred&email=fred%40sample.com&message=Hello%21&human=5&submit=Submit`
  
  - but let's focus on the last part of that URL - which is called the *query string*:
  
  `name=Fred&email=fred%40sample.com&message=Hello%21&human=5&submit=Submit`
  
  - you can see that the names of the form fields and their values are represented as **fieldName=value** pairs, and are separated by ampersands
  - also note that "special characters" like exclamation marks, the @ symbol, and spaces have been replaced with their URL encoded hexadecimal equivalents
  
  **Go ahead and change the `method` back to "post" - the form data will still be passed - but as a separate file that we don't see in the URL**
  
## V. <a id="section5">PHP code to handle the form
	
Here is the form and PHP code you will need to get everything working. Be sure to replace "abc1234@rit.edu" with your actual email address. Also, read the code comments! so that you understand what's going on:

**php-mail-3.php**

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Contact Us</title>
	<style>
	
	label {
		display:block;
		margin-top:20px;
		letter-spacing:2px;
	}
	
	#submit {
		display:block;
		margin-top:20px;
	}
	
	</style>
</head>
<body>
  	<h1>get in touch</h1>
 	<form method="post" action="<?php echo $_SERVER["PHP_SELF"];?>">
        
            <label>Name</label>
            <input name="name" placeholder="Type Here">
            
            <label>Email</label>
            <input name="email" type="email" placeholder="person@sample.com">
            
            <label>Message</label>
            <textarea name="message" placeholder="Type Here"></textarea>
            
            <label>*What is 2+2? (Anti-spam)</label>
            <input name="human" placeholder="Type Here">
            
            <input id="submit" name="submit" type="submit" value="Submit">
        
        </form>
 <?php   
 	// ** Form validation code **
 	// We will use the $_POST "super global" associative array to extract the values of the form fields
	// #1 - was the submit button pressed?
    if (isset($_POST["submit"])){ 
    	$to = "abc1234@rit.edu"; // !!! REPLACE WITH YOUR EMAIL !!!
    	
    	// #2 - if a value for the `email` form field is missing, give a default value
    	// else, use the value from the form field
			$from = empty(trim($_POST["email"])) ? "noemail@sample.com" : sanitize_string($_POST["email"]);
			
			$subject = "Web Form";
			
			// #3 - same as above, except with the `message` form field
			$message = empty(trim($_POST["message"])) ?  "No message" : sanitize_string($_POST["message"]);
			
			// #4 - same as above, except with the `name` form field
			$name = empty(trim($_POST["name"])) ? "No name" : sanitize_string($_POST["name"]);
			
			// #5 - same as above, except with the `human` form field
			$human = empty(trim($_POST["human"])) ? "0" : sanitize_string($_POST["human"]);
			
			$headers = "From: $from" . "\r\n";
			
			// #6 - add the user's name to the end of the message
			$message .= "\n\n - $name";
			
			// #7 - if they know what 2+2 is, send the message
			if (intval($human) == 4){
			
				// #8 - mail returns false if the mail can't be sent
				$sent = mail($to,$subject,$message,$headers);
				if ($sent){
					echo "<p><b>You sent:</b> $message</p>";
				}else{
					echo "<p>Mail not sent!</p>";
				}
			}else{
				echo "<p>You are either a 'bot, or bad at arithmetic!</p>";
			}

    }
    
    // #9 - this handy helper function is very necessary whenever
    // we are going to put user input onto a web page or a database
    // For example, if the user entered a <script> tag, and we added that <script> tag to our HTML page
    // they could perform an XSS attack (Cross-site scripting)
    function sanitize_string($string){
	$string = trim($string);
	$string = strip_tags($string);
	return $string;
    }
?>
</body>
</html>
```

- https://www.w3schools.com/php/php_forms.asp

## VI. <a id="section6">Test your form

- Try your form with and without various values like email or message - what happens?
- Type in a wrong answer for the 2+2 question - what happens?
- Type &lt;script> and other HTML tags into the form like below - what happens?

`<>Hi!</b><script>alert("XSS!");</script>`

- Now comment out the first 2 lines of code in `sanitize_string()`, reload the form, and type the above code into the message field. Be sure to test this in both Chrome and Firefox to see what happens.
	
## VII. <a id="section7">Styling your form

Replace the CSS in the form with the following - you should get a much better look.

The CSS for this form was borrowed and adapted from here: http://tangledindesign.com/how-to-create-a-contact-form-using-html5-css3-and-php/

```css
body {
		font-size:100%;
		font-family:Georgia, "Times New Roman", Times, serif;
	}

	h1{
		background-color:gray;
		color:white;
		text-align:center;
		padding:0 0 5px 0;
		font-variant: small-caps;
		font-size: 3em;
		font-family: Arial,Helvetica;
		margin:0;
	}

	form {
		width:459px;
		margin:0 auto;
	}

	label {
		display:block;
		margin-top:20px;
		letter-spacing:2px;
	}

	input, textarea {
		width:439px;
		height:27px;
		background:#efefef;
		border-radius:5px;
		border:1px solid #dedede;
		padding:10px;
		margin-top:3px;
		font-size:0.9em;
		color:#3a3a3a;
	}

	textarea {
		height:213px;
		font-family:Arial, Helvetica, sans-serif;
	}

	#submit {
		width:127px;
		height:38px;
		border:none;
		margin-top:20px;
		cursor:pointer;
		border: 1px solid gray;
		background-color:gray;
		color:white;
	}
```

**Which should give you something like this:**

![Screenshot](_images/php-mail-2.jpg)

## VIII. <a id="section8">Homework
- duplicate the contents of *php-mail-3.php* and name it **php-4-HW.php**
- add another field to the form:
    - it could be another text field for last name, ZIP code, or other information for example
    - or you could use another type of form element like a check box or radio button or a password field, that is up to you:
        - https://www.w3schools.com/html/html_form_elements.asp
        - https://www.w3schools.com/html/html_form_input_types.asp
- be sure that the contents of the new form field are incorporated into the email, and on the bottom of the page after the submit button is clicked!
- see the mycourses dropbox for due date

### Examples of completed homework

**Below we added a checkbox, and incorporated the results into the email:**

![Screenshot](_images/php-mail-3.jpg)

**And here is another example:**

![Screenshot](_images/php-mail-4.jpg)
	
<hr><hr>



| <-- Previous Unit | Home | Next Unit -->
| --- | --- | --- 
|   **[PHP Arrays (chapter 3)](php-3.md)** |  **[About this PHP Tutorial Series](php-0.md)** |  :-\
