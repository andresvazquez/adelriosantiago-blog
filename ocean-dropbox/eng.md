﻿<permalink>eng</permalink>
<month>9</month>
<year>2015</year>

# How to sync your Digital Ocean instance with Dropbox

One of the fastest ways to instantly deploy websites is to use Dropbox on your server. For sure you have used Dropbox or at least know how it works. It basically allows you to keep all your files sync'ed.
Uno de los modos más rapidos para instantaniamente deplorar sitios web es usando dropbox en tu server. De seguro has usado DropBox o al menos sabes cómo funciona. Basicamente de permite manetener todos tus archivos sincronizados

One of the most time consuming tasks while deploying a server is when you have to deploy your localhost changes into the real server and have to login to it and just do a `git pull`. If you are building a simple website, pure html, with no connections to databases and transactions you should try using Dropbox as your deploy tool.

Now let me be clear about two things: 
 - It is very well know that Dropbox is not exactly the safest tool out there... You should use **only** when the security is not a key factor (like when doing a landing page).
 - Also, Dropbox is not a "version control system" and it doesn't do anything to mitigate overwrite conflicts like GIT.

Also I think it using Dropbox as your version control system would look very unprofesional... Aside from that, if you are just rocking your startup, what are you waiting to use Dropbox as your deploy tool!?

Here are the steps to achieve that:

 - 
 - Download Dropbox on your machine -_-
 - 
 - Download the Dropbox daemon on your linux machine as explained on [this article](https://www.dropbox.com/install?os=lnx). If you need to know if you are running a 32 or 64 bits machine just type `uname -a`, a 32 bits machine withh throw something like:
 Linux discworld 2.6.38-8-generic #42-Ubuntu SMP Mon Apr 11 03:31:50 UTC 2011 i686 i686 i386 GNU/Linux
 While a 64 bits machine will throw something like:
 Linux discworld 2.6.38-8-generic #42-Ubuntu SMP Mon Apr 11 03:31:50 UTC 2011 x86_64 x86_64 x86_64 GNU/Linux
 - Now run the Dropbox daemon with `~/.dropbox-dist/dropboxd &`
 - Create a soft link from /var/www/html/yoursite to $HOME/Dropbox/yoursite, the index.html path is /var/www/html/yoursite/index.html
 - 
 - 
 - 
 - 

---


So that created this soft link: ln -s /var/www/html/lumston ./website


One of the fastest ways to sync your local changes and a real server is using Dropbox. 

Una de las maneras mas eficientes que hay para sincronizar una pagina web con tu projecto local es Dropbox. 

I recently tried to use Dropbox to sync one of my projects on my Digital Ocean instance. 


Pasos para sync de Dropbox
•	bajar dropbox en la computadora desktop
•	saber si es 32 bits o 64 bits la instancia de DO
o	uname –a
o	32  bits: Linux discworld 2.6.38-8-generic #42-Ubuntu SMP Mon Apr 11 03:31:50 UTC 2011 i686 i686 i386 GNU/Linux
o	Another 32 bits: Linux discworld 2.6.38-8-generic #42-Ubuntu SMP Mon Apr 11 03:31:50 UTC 2011 i686 i686 i686 GNU/Linux
o	64 bits:  Linux discworld 2.6.38-8-generic #42-Ubuntu SMP Mon Apr 11 03:31:50 UTC 2011 x86_64 x86_64 x86_64 GNU/Linux
•	Install the script from https://www.dropbox.com/install?os=lnx
•	Run the deamon with ~/.dropbox-dist/dropboxd & (segun yo si se reuqiere el &) 
•	Create a link from /var/www/html/yoursite to $HOME/Dropbox/yoursite, the index.html path is /var/www/html/yoursite/index.html
•	For example the index.html file of the site I wanted to sync is at /var/www/html/site/index.html, therefore I created the following link to the $HOME/Dropbox folder:
ln –s 



