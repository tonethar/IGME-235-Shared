# How to post to RIT's *banjo* web server

1. Fire up your preferred FTP client (FileZilla is free and cross platform)
1. Enter the following information:
    - **Host/Server:** *banjo.rit.edu*
    - **Username:** your *abc1234* id
    - **Password:** your RIT password
    - **Port:** SFTP (or 22)
1. Click the *Connect* button or similar to connect to banjo
1. Upload your files to the `www` folder or a sub-directory of `www`
1. Set the file permissions to `644` for files and `755` for folders. You can usually do this by right-clicking on each file and choosing "properties" or "permissions"
1. Be sure to confirm that your files have been properly posted by pointing a browser at `http://people.rit.edu/abc1234` - note that the `www` folder is NOT in the URL after your username.
