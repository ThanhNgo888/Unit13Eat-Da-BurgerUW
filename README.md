# HW13-Eat-Da-Burger
Node Express Handlebars

Overview
In this assignment, you'll create a burger logger with MySQL, Node, Express, Handlebars and a homemade ORM (yum!). Be sure to follow the MVC design pattern; use Node and MySQL to query and route data in your app, and Handlebars to generate your HTML.

Read This
When trying to connect remotely to your Heroku database on an open network such as a coffee shop, library, or even your University WiFi, it will be blocked. If you are experiencing a Heroku connection error, this could be why.

Important


This assignment must be deployed. Be sure to utilize the MYSQL Heroku Deployment Guide in order to deploy your assignment.


Before You Begin


Eat-Da-Burger! is a restaurant app that lets users input the names of burgers they'd like to eat.


Whenever a user submits a burger's name, your app will display the burger on the left side of the page -- waiting to be devoured.


Each burger in the waiting area also has a Devour it! button. When the user clicks it, the burger will move to the right side of the page.


Your app will store every burger in a database, whether devoured or not.


Check out this video of the app for a run-through of how it works.



Commits
Having an active and healthy commit history on GitHub is important for your future job search. It is also extremely important for making sure your work is saved in your repository. If something breaks, committing often ensures you are able to go back to a working version of your code.


Committing often is a signal to employers that you are actively working on your code and learning.


We use the mantra “commit early and often.”  This means that when you write code that works, add it and commit it!


Numerous commits allow you to see how your app is progressing and give you a point to revert to if anything goes wrong.




Be clear and descriptive in your commit messaging.

When writing a commit message, avoid vague messages like "fixed." Be descriptive so that you and anyone else looking at your repository knows what happened with each commit.



We would like you to have well over 200 commits by graduation, so commit early and often!



Submission on BCS


This assignment must be deployed. * Please submit both the deployed Heroku link to your homework AND the link to the Github Repository!


Instructions

App Setup


Create a GitHub repo called burger and clone it to your computer.


Make a package.json file by running npm init from the command line.


Install the Express npm package: npm install express.


Create a server.js file.


Install the Handlebars npm package: npm install express-handlebars.


Install MySQL npm package: npm install mysql.


Require the following npm packages inside of the server.js file:

express




DB Setup


Inside your burger directory, create a folder named db.


In the db folder, create a file named schema.sql. Write SQL queries this file that do the following:

Create the burgers_db.
Switch to or use the burgers_db.
Create a burgers table with these fields:


id: an auto incrementing int that serves as the primary key.

burger_name: a string.

devoured: a boolean.





Still in the db folder, create a seeds.sql file. In this file, write insert queries to populate the burgers table with at least three entries.


Run the schema.sql and seeds.sql files into the mysql server from the command line


Now you're going to run these SQL files.


Make sure you're in the db folder of your app.


Start MySQL command line tool and login: mysql -u root -p.


With the mysql> command line tool running, enter the command source schema.sql. This will run your schema file and all of the queries in it -- in other words, you'll be creating your database.


Now insert the entries you defined in seeds.sql by running the file: source seeds.sql.


Close out of the MySQL command line tool: exit.





Config Setup


Inside your burger directory, create a folder named config.


Create a connection.js file inside config directory.


Inside the connection.js file, setup the code to connect Node to MySQL.


Export the connection.




Create an orm.js file inside config directory.


Import (require) connection.js into orm.js


In the orm.js file, create the methods that will execute the necessary MySQL commands in the controllers. These are the methods you will need to use in order to retrieve and store data in your database.

selectAll()
insertOne()
updateOne()



Export the ORM object in module.exports.





Model setup


Inside your burger directory, create a folder named models.


In models, make a burger.js file.


Inside burger.js, import orm.js into burger.js


Also inside burger.js, create the code that will call the ORM functions using burger specific input for the ORM.


Export at the end of the burger.js file.







Controller setup


Inside your burger directory, create a folder named controllers.


In controllers, create the burgers_controller.js file.


Inside the burgers_controller.js file, import the following:

Express
burger.js



Create the router for the app, and export the router at the end of your file.



View setup


Inside your burger directory, create a folder named views.


Create the index.handlebars file inside views directory.


Create the layouts directory inside views directory.


Create the main.handlebars file inside layouts directory.


Setup the main.handlebars file so it's able to be used by Handlebars.


Setup the index.handlebars to have the template that Handlebars can render onto.


Create a button in index.handlebars that will submit the user input into the database.







Directory structure
All the recommended files and directories from the steps above should look like the following structure:
.
├── config
│   ├── connection.js
│   └── orm.js
│ 
├── controllers
│   └── burgers_controller.js
│
├── db
│   ├── schema.sql
│   └── seeds.sql
│
├── models
│   └── burger.js
│ 
├── node_modules
│ 
├── package.json
│
├── public
│   └── assets
│       ├── css
│       │   └── burger_style.css
│       └── img
│           └── burger.png
│   
│
├── server.js
│
└── views
    ├── index.handlebars
    └── layouts
        └── main.handlebars
============================================================================================================
Set up Database Node.js Burger Application using express, express handlebars, body parser and MySQL
1. install package.json
npm init -y
2. install node modules packages
npm install express express-handlebars body-parser mysql.
3. install nodemon globally ->serer that refreshes automatically development.
npm install -g nodemon
->package.json:
"scripts":{
    "start": "node server.js",
    "dev": "nodemon serer.js"
}
4. create our database using mySQL workbench
In db folder:
schema.sql
copy data in schema and paste in myworkbench ->run ->refresh-> to create burger database and table ->Now we have our table created.

seeds.sql
copy data in seeds file and paste in myworkbench and select all ->run it -> 
check it out and run a query:
SELECT * FROM burgers -> run it -> should see the burger column and database now is ready to use.
=============================================================================================================
check to see if nodemon is working:
npm run dev



