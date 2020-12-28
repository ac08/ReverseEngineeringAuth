# Unit-14-Sequelize-Homework-Reverse-Engineering-Code

------------------------------------------------------------------------------------------------------------------------------

--PASSWORD AUTHENTICATION APPLICATION--

This Node-Express-SQL application allows users to create an account, log into the account and sign back out securely. All user data is stored in a mysql database.

------------------------------------------------------------------------------------------------------------------------------

--THE USER STORY--

As someone who wants to safely log in to "Z" application or server, I want to know my personal details are safely stored so that I dont have to worry about using "Z".

------------------------------------------------------------------------------------------------------------------------------

--TECHNOLOGY STACK USED --

- EXPRESS is the web-framework built for Node.js.
- EXPRESS-SESSION is used to create a session middleware with given *options*.
- PASSPORT is an Express-compatible authentication middleware for Node.js.
- PASSPORT-LOCAL is a strategy for authenticating with a username and password.
- BCRYPTJS is an optimized bcrypt in JavaScript with zero dependencies
- MYSQL2 is a Mysql client module for Node.js.
- SEQUELIZE is a promise-based Node.js ORM.

------------------------------------------------------------------------------------------------------------------------------

--HOW TO GET STARTED--

To begin using this app, please clone this repository on your local drive. Once this is complete, please proceed with the following steps:

1) Create a mysql db called 'passport_demo'
2) Navigate to the config folder, open config.json and insert your personal data (ie) username, password
3) Open Node.js bash terminal for the current repository and run "npm i" to install all node packages
4) Also in terminal, run "npm start" or if in dev-mode "npm run watch" and you will be connected to server
5) Open Google Chrome and navigate to "http://localhost:8080"
6) The Node-Express-MySQL application is ready to be used!

------------------------------------------------------------------------------------------------------------------------------

--ALL FILES EXPLAINED--

CONFIG DIRECTORY

  MIDDLEWARE SUBDIRECTORY
  
  `isAuthenticated.js {
    restricts routes that user is not allowed to visit if not logged in. if user is logged in, it continues with request };`

  `config.json {
    connection configuration information };`
  
  `passport.js {
    tells passport we want to use a Local Strategy. In other words, we want login with a username/email and password };`

MODELS DIRECTORY

  `index.js {
    connects to database and imports users log in data };`
  
  `user.js {
    imports "bcrypt" for password hashing. This will make our database secure even if compromised. Also here is the JavaScript used to define what is stored on our database (User table) };`
  
ROUTES DIRECTORY

  `api-routes.js {
    holds routes for signing in (*/api/signup*), logging out (*/logout*) and getting users specific data (*/api/user_data*) to be displayed client side };`
  
  `html-routes.js {
    holds routes that check whether user is signed in, or if the user already has account; and sends them tio the correct html page };`
  
`package.json {
  contains all Node.js package info, node modules used, version info and much more specific to the node project };`

`server.js {
  file is backbone of the application. This file requires necessary npm packages, sets up a dynamic PORT, sets up the express app and associated middleware for data parsing, establishes some config information for password authentification, imports routes file and configs hooks them up to the web-server, and finall it will sync the database / logs message in terminal on successful connection to the web-server };`

------------------------------------------------------------------------------------------------------------------------------
