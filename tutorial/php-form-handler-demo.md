# PHP Form Handler Demo

- In [4 - PHP Mail & Forms](./php-4.md) we learned how to create a PHP form that gathered email information, and "called itself" after the submit button was clicked.
- But sometimes, we would like for a form on an HTML page to call PHP code located in a *different* file - for example - a form located on your HTML portfolio page that would need call a mail script located in an external PHP file
- The two files (HTML & PHP) you need to do this are below 

## I. HTML Form

- The form on the HTML file below has an `action` of **form-handler.php**, which means that it will call this PHP file when the submit button is pressed


**form.html**
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
 	<form method="post" action="form-handler.php">
        
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

## II. PHP Script

- Below we have modified the PHP from the other exercise to work with the above form
- Two things are different from the previous version of this code:
  - we are not going to echo out a confirmation that the mail was successfully sent, instead after sending the mail ...
  - the code will re-direct back to the page the form is on with this line of PHP code: `header("Location: form.html");`
- note that if this script echos out anything at all, then the redirect back to the form will **FAIL!**
  - that means that there must not be any `echo()` statements in your PHP code
  - there must also NOT be any HTML or even blank lines *outside* of your PHP code in **form-handler.php** below. Even a single blank line will "break" the re-direct back to **form.html**

**form-handler.php**

```php
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
		// if ($sent){
// 					echo "<p><b>You sent:</b> $message</p>";
// 		}else{
// 					echo "<p>Mail not sent!</p>";
// 		}
	}else{
				// echo "<p>You are either a 'bot, or bad at arithmetic!</p>";
	}
    }
    
    // go back to form page when we are done
	header("Location: form.html"); // #10 - CHANGE THIS TO THE NAME OF YOUR FORM PAGE - AN ABSOLUTE URL WOULD BE EVEN BETTER
	exit();
    
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
```
