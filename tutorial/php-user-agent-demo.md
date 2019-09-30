# Using PHP to detect the HTTP *User-Agent string*

## I. Overview
- In software development, a **user agent** is software that acts on behalf of a user. In the HTTP protocol, a user agent is a client application that submits HTTP requests. Examples of HTTP clients include web browsers, 'bots such as search engine web crawlers, and apps that consume HTTP services (weather, stock quotes, etc)
- In HTTP, the client sents a **user-agent string** that contains a list of keywords and comments that are designed to communicate the client's capabilities to the server. For example, the User-Agent string might be used by a web server to filter web assets based on the known capabilities of a particular version of client software. ex. A "flip phone" would not receive a web site's images and CSS style sheets.

## II. Examples of User-Agent strings
- The user-agent string includes:
  - the application type
  - operating system
  - software vendor or software version
- In HTTP, this information is sent by the client as a HTTP *request header*
- Here are some sample user agent strings:

**Chrome on Mac OS:**
`Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.106 Safari/537.36`

**Firefox on Android Mobile:**
`Mozilla/5.0 (Android; Mobile; rv:14.0) Gecko/14.0 Firefox/14.0`

**iPhone:**
`Mozilla/5.0 (iPhone; CPU iPhone OS 8_0_2 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12A366 Safari/600.1.4`

**GoogleBot:**
`Googlebot/2.1 (+http://www.googlebot.com/bot.html)`

**Amazon Kindle 3:**
`Mozilla/5.0 (Linux; U; en-US) AppleWebKit/528.5+ (KHTML, like Gecko, Safari/528.5+) Version/4.0 Kindle/3.0 (screen 600x800; rotate)`
  
**Pantech Feature Phone:**
`PantechP7040/JLUS04042011; Mozilla/5.0 (Profile/MIDP-2.0 Configuration/CLDC-1.1; Opera Mini/att/4.2.16479; U; en-US) Opera 9.50`

## III. What's my user-agent string?

- point your browser here to see it: https://www.esolutions.se/whatsmyinfo
- or post this PHP script to your people.rit.edu account:

**user-agent.php**
```php
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title></title>
</head>
<body>
  <?php 
    $useragent = $_SERVER['HTTP_USER_AGENT'];
    echo "<p>Your browser's user agent string is: $useragent</p>"; 
  ?>
</body>
</html>
```

## IV. Filtering the HTML based on the user-agent

Here is a simple program that will deliver different HTML to a device depending on whether it is a iPad, iPhone, or Android device. If the device is none of these, it will receive a default HTML page. 

**user-agent-demo.php**
```php
<?php
  // https://github.com/serbanghita/Mobile-Detect/blob/master/Mobile_Detect.php

  // 1 - grab the browser's declared user-agent string from the $_SERVER "superglobal"
  $useragent = $_SERVER['HTTP_USER_AGENT'];

  // 2 - This will be the default HTML we will display
  $html = "<h1>Here's some 'desktopish' HTML</h1>";

  // 3 - but if the user-agent string contains "iPhone", use this HTML instead
  if (strpos($useragent, "iPhone") !== false) {
    $html = "<h1>Here's some 'iPhoneish' HTML</h1>";
  }

  // 4 - but if the user-agent string contains "iPad", use this HTML instead
  if (strpos($useragent, "iPad") !== false) {
    $html = "<h1>Here's some 'iPadish' HTML</h1>";
  }

  // 5 - but if a device is an Android, use this HTML instead
  if (strpos($useragent, "Android") !== false) {
    $html = "<h1>Here's some 'Androidish' HTML</h1>";
  }
?>

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title></title>
</head>
<body>
  <?php 
    echo $html;
    echo "<p>BTW - your browser's user agent string is: <b>$useragent</b></p>"; 
  ?>
</body>
</html>
```

Above we are sending meaningless HTML, but you could modify this script to instead send optimized HTML/CSS to the mobile phones. For example, you could send mobile phones a version of your page that lacked external style sheets and instead used embedded styles (in the &lt;head> section). The advantage of doing this is that the phones will not have to make an additional request for a CSS file over a high latency cell connection.

## V. Altering the User-Agent string
- To test the above script, you can try it out with multiple devices, or you can just tell the browser to send a different user-agent string. Recall that the user-agent string is communicated to the server through an HTTP request header, and there is no way for the server to authenticate what kind of device is requesting a resource.
- Here is a Chrome extension that allows you to easily do this: [User-Agent Switcher for Google Chrome](https://chrome.google.com/webstore/detail/user-agent-switcher-for-g/ffhkkpnppgnfaobgihpdblnhmmbodake)

## VI. Discussion
- An alternative to browser sniffing and "forked" HTML is to instead use [CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- What this does is that server send the same HTML to all user agents, but the individual browser will decide which CSS rules (and/or CSS files) to use based on the *capabilities* of the web browser i.e. screen size, screen color depth, screen orientation, etc
- We will be learning about media queries in this course very soon!

## VII. Reference
- https://en.wikipedia.org/wiki/User_agent
- https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol
- https://en.wikipedia.org/wiki/List_of_HTTP_header_fields
- https://www.w3.org/Protocols/HTTP/HTRQ_Headers.html#user-agent
- https://github.com/yzalis/UAParser (a PHP User-Agent string sniffing library)

