# SIMPLE TO-DO APPLICATION ON MERN WEB STACK

In this project, you are tasked to implement a web solution based on MERN stack in AWS Cloud.

# MERN Web stack consists of following components:

- MongoDB: A document-based, No-SQL database used to store application data in a form of documents.

- ExpressJS: A server side Web Application framework for Node.js.

- ReactJS: A frontend framework developed by Facebook. It is based on JavaScript, used to build User Interface (UI) components.

- Node.js: A JavaScript runtime environment. It is used to run JavaScript on a machine rather than in a browser.

# Step 0 – Preparing prerequisites

As seen in project 1 & 2, this project require will need an AWS account and a virtual server with Ubuntu Server OS.



# Step 1 – Backend configuration

- Update ubuntu:

   sudo apt update

- Upgrade ubuntu:

  sudo apt upgrade

- Lets get the location of Node.js software from Ubuntu repositories:

   curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

- Install Node.js with the command below:

   sudo apt-get install -y nodejs

- The command above installs both Node and NPM packages.

- To Verify the version of Nodejs and NPM installed, run the command below:

    node -v; npm -v

You should see an image like the one below on your terminal:


![Npm Node verification](https://user-images.githubusercontent.com/65022146/189549532-b7eac2d8-2c24-4798-8004-c8e83596aab9.png)



- Create a new directory for your To-Do project:

   mkdir Todo

- Changed into Todo directory with the command below:

   cd Todo

- Initialise a project by running the command below:

   npm init


- When prompted answer accordingly and you should see something like the screenshot below:



![Creating a new file 'Package  json via npm init command](https://user-images.githubusercontent.com/65022146/189550158-7e477a7a-76d2-4b0a-a063-d425bd4962ef.png)




# Install ExpressJS

- Install Express using npm:

   npm install express

- create a file index.js with the command below:

   touch index.js

- Install the dotenv module:

  npm install dotenv

- Open the index.js file with the command below:

   vi index.js

- In the blank open file, paste and save the text below:

 
 const express = require('express');
  require('dotenv').config();

  const app = express();

  const port = process.env.PORT || 5000;

  app.use((req, res, next) => {
  res.header("Access-Control-Allow-Origin", "\*");
  res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
  next();
  });

  app.use((req, res, next) => {
  res.send('Welcome to Express');
  });

  app.listen(port, () => {
  console.log(`Server running on port ${port}`)
  });


- Now run the command below:

   node index.js

- You should find something like the image below:


![Server running on Port 5000](https://user-images.githubusercontent.com/65022146/189550415-448c2357-d4a8-4447-9e64-97f4b8111e63.png)


