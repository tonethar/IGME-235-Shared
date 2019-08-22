# htaccess Demo
*A .htaccess ("hypertext access") file is a directory-level configuration file supported by the major web servers, used for configuration of site-access issues, such as URL redirection, URL shortening, Access-security control (for different webpages and files), and more.*

In class, let's take a look at what .htaccess files can do. We will look at the following htaccess directives:

1. `DirectoryIndex hello.html` - makes the default file for the folder *hello.html* rather than *index.html*
2. `Options -Indexes` - turns off file listing for folders so that users can't see your files and folders directly
3. `Header add X-HeaderName "Header Value"` - sends a custom header. `X-` is a convention used for naming non-standard headers
4. `Redirect /~acjvks/230/hello.html http://www.rit.edu` - redirects the browser from a file to another domain
5. `Redirect /~acjvks/230/ /~acjvks/110/` - redirects the browser from a folder, to a different folder
6. `ModPagespeed off` - turns off the ModPagespeed extension
