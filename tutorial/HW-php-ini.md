# Homework - Configuring *php.ini*

## I. Overview

* A configuration file - **php.ini** - is read when PHP starts up.
* This file contains directives you can set to configure your PHP setup, and controls certain capabilities of how PHP runs for you on `banjo.rit.edu`
* Each of you have a *php.ini* file located on your banjo account. In this exercise we are going to make two small changes to this file. 

## II. Fetch your *php.ini* file, and make a back-up copy

1. Download your banjo *php.ini* file to your local computer. It is located in your login directory on banjo at `abc1234/php_data/php.ini`

2. Now that you have a copy of the *php.ini* file on your computer, change the name of the original file on the banjo server from *php.ini* to **php.ini_bak**

Note : *php.ini_bak* should be kept on banjo as a backup copy that you can always go back to, in case there is a problem with the changes you are going to make to *php.ini*


## III. Now let's make some changes to your *php.ini* file

3. First we will turn on error reporting so that you can see php errors printed to the browser window. This is a great option to have turned on during PHP development. Locate the line that looks like: 

`display_errors = Off `

(it should be around line # 355) and change it to:

 `display_errors = On`


4. Second, we will give PHP the ability to download files from other domains. We will need this ability later in the course when we are downloading web pages to scrape, and JSON/XML files to parse. Locate the line that looks like: 

`allow_url_fopen = Off`

(it should be around line # 578) and change it to:

 `allow_url_fopen = On`


5. Save your changes, and transfer this updated *php.ini* file back to the directory that you got it from.


## IV. Test to see if you are getting PHP error messages

6. Create a script named **broken.php** to test error display and upload it to banjo in a folder you need to create -  `www/230/test/`  - run it in the browser, you should see "Parse error" message in the browser window when the page is loaded.

**broken.php** 
```
<?php
	echo "Welcome!!!!  // missing closing quote and semicolon
?>
```

**The full error message you will get looks something like this:**

```
Parse error: syntax error, unexpected end of file, expecting variable (T_VARIABLE) or ${ (T_DOLLAR_OPEN_CURLY_BRACES) or {$ (T_CURLY_OPEN) in /home/acjvks/www/230/test/broken.php on line 3
```

**The corrected version of *broken.php* is here:**

```
<?php
	echo "Welcome!!!!";  // all good!
?>
```

7. Another way to see error messages is to run PHP scripts on the command line. You can do this by establishing an ssh session with `banjo.rit.edu`, then `cd` to the folder with *broken.php* in it (which is `230/test/`), and then type:

`php broken.php`

This runs *broken.php* through the command-line PHP parser, and should also display the error message.


8. Can you fix *broken.php* right here on the command line with a text editor like `nano`? Make it so!


9. Another place to see error messages is in the PHP error log file on banjo at `abc1234/php_data/php.log`

- Note: If you do not find php.log in your php_data folder, you may need to edit your php.ini file to add the path to your user account.  Find the following line:

   `error_log = "##HOMEDIR##/php_data/php.log"`

   and replace it with

   `error_log = "/home/abc1234/php_data/php.log"`
   *(replace abc1234 with your userid)*


## V. Test to see if PHP can open remote files
10. Now we will check to see if we can open a file on another server with the following script, which you can name **open.php** and put in your `230/test/` folder.

**open.php**
```
<?php
	$data = file_get_contents("http://www.cia.gov"); // or any other URL you want to use
	echo "<h1>Here's your data!!</h1>";
	echo $data;
 ?>
```

11. Test this in the browser by loading *open.php*  - the script should load the default page for your chosen URL and display it. 

12. Test this on the command line by typing `php open.php` from the correct directory. You should see the default page for your chosen URL dumped to the console.

## VI. Wrap up
- Hopefully you can see how useful it is to understand how to edit your account's *php.ini* file. A reference to what all of these PHP directives mean can be found at: http://www.php.net/manual/en/ini.list.php
- Another capability that PHP has is to change these initialization setting on a *per-script* basis. See the documentation for the PHP `ini_set()` function at: http://php.net/manual/en/function.ini-set.php

## VII. Submission
See dropbox for due date.

<hr><hr>

**[Table of Contents <- About this PHP Tutorial Series](php-0.md)**
