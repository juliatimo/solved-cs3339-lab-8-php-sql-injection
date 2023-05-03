Download Link: https://assignmentchef.com/product/solved-cs3339-lab-8-php-sql-injection
<br>
<h1>PART 1: SQL INJECTION TUTORIAL</h1>

<strong> </strong>

Go through the SQL injection tutorial at

<u>https://free.codebashing.com/free-content/php/sql_injection</u>




Once you finish answer this question:

<strong>How can you best prevent SQL injection attacks? (Do some research) </strong>

<strong> </strong>

<strong> </strong>

<h1>PART 2: SETUP</h1>




<ol>

 <li>Login to your Kali instance</li>

 <li>Run the following commands from the terminal</li>

</ol>




apt update  apt install apache2  /etc/init.d/apache2 start

/etc/init.d/mysql start apt -y install php7.3 libapache2-mod-php7.3

service apache2 restart  service mysql restart

<strong> </strong>

<ol start="3">

 <li>Open MySQL in your terminal with the command: mysql Run the commands:</li>

</ol>




CREATE DATABASE test;     quit;

<strong> </strong>

<ol start="5">

 <li>Copy the contents of the <strong>Lab 8/html</strong> folder (from the .zip you downloaded for this assignment) into<strong> /var/www/html </strong></li>

</ol>




You can also get the zip file from here: <u>https://s2.smu.edu/~rtumac/cs3339/spring2020/Lab8/</u>




<ol start="6">

 <li>Run the following command:</li>

</ol>

<strong>     </strong>mysql test &lt; create_db.sql




<ol start="7">

 <li>Go back to the MySQL terminal. Run the following commands: Create new user:</li>

</ol>

CREATE USER ‘userhere’@’%’ IDENTIFIED BY ‘passwordhere’;




Grant permissions to user:

GRANT ALL PRIVILEGES ON *.* TO ‘userhere’@’%’ WITH GRANT OPTION; flush privileges;

<ol start="8">

 <li>Update new MySQL information in two files:</li>

</ol>

<strong>checklogin.php searchResult.php </strong>

<strong> </strong>

<strong> </strong>

<h1>PART 3</h1>

<strong> </strong>

Open a web browser and navigate to <strong>localhost/login.html </strong>




You can use the username: <strong>john</strong> and password: <strong>1234</strong> to login.

Your goal here is to NOT use that username or password to login to the website, instead use SQL injection.




Use what you learned from the tutorial in part 1 and what you can find online to help you login using SQL injection instead of the correct username and password.




<strong>What input did you use to complete this action? Specify your inputs on each field </strong>

<strong> </strong>

<strong> </strong>

<h1>PART 4</h1>

<strong> </strong>

Now that you have logged in, navigate to localhost/search.html




This page has a basic search functionality to search for messages in a database. Some of these messages are public and others are private. This search bar only allows you to search for the public messages. Using SQL injection, get the search function to return all of the messages, both public and private.

<strong> </strong>

<h2>What input did you use to complete this action? Specify your inputs on each field PART 5</h2>

<strong> </strong>

You have discovered that the name of the table that stores user information is members.




Go back to the localhost/login.html and use SQL injection to drop the table members from the database.




<strong>What input did you use to complete this action? Specify your inputs on each field </strong>




<strong> </strong>

<h1>PART 6</h1>

<strong> </strong>

<strong>Open up the file /var/www/html/checklogin.php in a text editor. This is the php file that is used to verify you have the correct username and password. As you have just seen, it does not work very well. Edit this file to help prevent SQL injection attempts. </strong>

<strong> </strong>

<h1>This may take a bit of research. HINT: Google ‘mysqli prevent sql injection’</h1>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>WHAT TO TURN IN </strong>

<strong> </strong>

<h2>1. Document containing your answers to the questions highlighted in red 2. Edited checklogin.php and an explanation of how its security flaws were addressed</h2>

<strong> </strong>