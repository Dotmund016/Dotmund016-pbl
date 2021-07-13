# Web Stack Implementation (Lamp Stack) In Aws
## What is a Technology stack?
A technology stack is a set of frameworks and tools used to develop a software product. This set of frameworks and tools are very specifically chosen to work together in creating a well-functioning software. They are acronymns for individual technologies used together for a specific technology product. some examples are…

LAMP (Linux, Apache, MySQL, PHP or Python, or Perl)
LEMP (Linux, Nginx, MySQL, PHP or Python, or Perl)
MERN (MongoDB, ExpressJS, ReactJS, NodeJS)
MEAN (MongoDB, ExpressJS, AngularJS, NodeJS

AWS account was first opened and a free tier was signed up to spin up an EC2 instance for ubuntu

## Connecting to EC2 terminal
### Connecting to EC2 using Putty
![Screenshot P1](https://user-images.githubusercontent.com/87065881/125520475-8625ca30-bdee-4ec6-b934-0817e44786cb.png)

Apache HTTP Server was installed with TCP port 80 opened on our EC2 Machine
![Screenshot Apt 2](https://user-images.githubusercontent.com/87065881/125520962-e334d5a1-3f7e-4ed5-b010-bbc116baec56.png)

## Installing Mysql
Now that you have a web server up and running, we needed to install a Database Management System (DBMS) to be able to store and manage data for your site in a relational database
## Installing Php
Apache was then installed to serve our content and MySQL installed to store and manage our data.
![Apache HTTP Server](https://user-images.githubusercontent.com/87065881/125523598-07910d04-62da-43fc-9b8e-84834f2c1d26.png)

## Creating A Virtual Host For Your Website Using Apache
A domain called projectlamp (directory) was created by adding to the default /var/www/html directory
sudo mkdir /var/www/projectlamp
I assigned ownership of the directory with the current system user
sudo chown -R $USER:$USER /var/www/projectlamp
Then, created and open a new configuration file in Apache’s sites-available directory using your preferred command-line editor.
This created a new blank file and the givenbare-bones configuration was pasted and saved
The site available directory was tested, enated and config tested and the Apache’s default website was disabled so as not to override our virtual host 
Then apache was reloaded and an index file was created and inserted in the empty web root projectlamp to be working when tested with the public ip
![Screenshot virtual host using DNS](https://user-images.githubusercontent.com/87065881/125526377-1c284df8-c53d-43c1-bd1f-e78d6166e485.png)
## Enable Php On The Website
With the default DirectoryIndex settings on Apache, a file named index.html will always take precedence over an index.php file.
This sequence was then changed to give preference for the .php
Then Created a new file named index.php inside your custom web root folder:
vim /var/www/projectlamp/index.php
This open a blank file, and a valid PHP code was pasted inside the file:

<?php
phpinfo();
When it was saved and the website refreshed the php showed up as seen below 
![Screenshot PhP version](https://user-images.githubusercontent.com/87065881/125527065-21858683-c3f5-4340-ae95-3f2722f59831.png)
Aterwards the command sudo rm /var/www/projectlamp/index.php was used to remove the fileas it showed the information of PHP environment -and your Ubuntu server.
