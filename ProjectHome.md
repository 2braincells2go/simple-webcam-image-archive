Simple Webcam Image Archive Script

---


Author: Stephen Phillips - http://www.stephen-phillips.co.uk/webcam.html

Created Date: 11/03/2012
Last Modified Date: 30/04/14

Version: 1.12

Updated to fix some minor bugs and issues in the code.

Description:

This is a simple script I wrote to automatically archive images from my webcam to a MySQL Database for me to view later using PHP and a scheduler such as cron.

It is very simple, and can be included into a page using an iframe, it automatically copies the latest version of an image to the database which can be viewed using gallery.php to view all with sorting options,
or using recentListing.php which shows the 10 most recent images archived.

Installation

---


1. Grab a copy of the source here on Google Code or download the latest version of the files from http://www.stephen-phillips.co.uk/webcam/webcam.zip

2. Extract the webcam.zip archive.

3. Create a mysql db called something like `webcam` and upload the contents of the sql file `webcam.sql` in the folder /db to it

4. Edit the config.inc.php in the inc folder to contain your website details and the database details.

5. Upload the folder to your server (keeping it in the /webcam directory otherwise you will have to edit it).

6. Setup your crontab to contain the following line, which copies the file every 10 minutes, edited for your own website and server

```
*/10 * * * * curl http://www.yourwebsite.co.uk/webcam/snapshot.php >/dev/null 2>&1
```

7. Embed either gallery.php or recentListing.php in your website using the following code or link directly to them.

```
<iframe src="http://www.yourwebsite.co.uk/webcam/gallery.php" width="1024" height="768" scrolling="yes" frameborder="no"></iframe>
```
```
<iframe src="http://www.yourwebsite.co.uk/webcam/recentListing.php" width="1024" height="200" scrolling="no" frameborder="no"></iframe>
```

8. I have included a very basic and simple javascript webcam script in the page index.html which will update an image src every 15 seconds without reloading the page or doing a meta refresh,
this can be used in conjunction with an ftp upload of an image from your webcam and will update every 15 seconds, Feel free to play and style it!

Future Development

---

I am hoping to rewrite this at some point soon using Socket.IO (http://socket.io/) and node.js (http://nodejs.org/) as I have been reading a lot of good things of late regarding Socket.IO and loading binary data such as images!

Finally

---


You can see the script in action on my website over at http://www.stephen-phillips.co.uk/webcam.html

Have Fun,

And feel free to email me at me@stephen-phillips.co.uk with comments and suggestions!