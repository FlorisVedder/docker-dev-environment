Docker Development Environment
- apache
- mysql

Based on this instruction/tutorial:
https://www.kinamo.be/en/support/faq/setting-up-a-development-environment-with-docker-compose

### SETUP ###
Clone this project in a directory of choice:
git clone git@github.com:FlorisVedder/docker-dev-environment.git my-new-directory

Create a www directory inside the php directory so you end up with:
my-new-directory/php/www

The 'www' directory is your webroot, so index.php should be placed in www.
When you start your docker machine it's webroot points to this www.
So your docker (virtual) machine reads the www while it's a folder on your host systeem (your desktop or laptop). In this way you can create files that stay, also when the docker machine is closed.

For test purpose creat your index.php in the www directory so you end up with:
my-new-directory/php/www/index.php
With something in it like:
<?php
phpinfo();
?>

### START YOUR DOCKER MACHINE ###
somewhere in my-new-directory fire the command:
docker-compose up


### VISIT YOUR (test) SITE ### 
when docker is up and running you see the process in your terminal
one of these lines that start with php_1 contains the ip address, something like: 172.20.0.3
find this address and paste it in the browser like: http://172.20.0.3 

### MYSQL ###
If you want to know the user and password for mysql take a look at the docker-compose.yml file
There you'll see something like:
      environment:
       - MYSQL_ROOT_PASSWORD=7TsTChbR
       - MYSQL_DATABASE=axvDFen6

### THAT'S ALL ###
