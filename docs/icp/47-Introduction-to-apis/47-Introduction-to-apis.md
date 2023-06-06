---
title: Introduction To API
description: "Introduction To API"
hide_table_of_contents: true
---

## Introduction To API

An API **Application Programming Interface** is a set of rules and protocols that allows different software applications to communicate and interact with each other. In the context of web development, APIs are used to enable communication between the `frontend` (client-side) and `backend` (server-side) of a web application.

**Frontend :** The frontend, also known as the `client`, refers to the user interface of a web application that users interact with. It is responsible for sending requests to the backend and displaying the data received from the server.

**Backend :** The backend, also known as the server, handles the processing of requests received from the frontend. It performs various operations such as retrieving data from a database, executing business logic, and generating a response to be sent back to the client.

**API :** The API acts as an intermediary between the frontend and backend. It defines a set of rules and protocols for how requests and responses should be structured. The API takes the requests from the frontend, processes them, and transforms the data as required. It then sends the transformed data back to the frontend as a response.

<img src="/icp/47/step-1.jpg" alt="step-1" height="300px"/>

## Backend Commands:

1. **npm init -y :** This command initializes a new Node.js package in the current directory. The -y flag sets default options for all the prompts, allowing the initialization to proceed without requiring user input.

```js
      npm init -y
```

2. **Create index.js** This step involves creating an index.js file. The index.js file typically serves as the entry point of the backend application.

3. **edit package.json :** The package.json file contains metadata about the Node.js package and its dependencies. This step likely involves editing the package.json file to include necessary information about the backend application.

<img src="/icp/47/step-2.png" alt="step-2" height="300px"/>

## Expree js:

Express.js is a popular JavaScript framework for building web applications and APIs. It simplifies the process of setting up a server and handling HTTP requests and responses.

### Install express :

To install express, you can use the following commands:

```js
npm install express
```

### How to create server :

To create a server using Express, you need to write some code in your index.js file. Here's an

**Example :**

```js
express;
import express from "express";

const app = express();

app.listen(5000, () => {
  console.log("listening on port 5000");
});
```

In the above code:

- We import the express module and create an instance of the express application.
- The app.listen() method starts the server and makes it listen on port 5000.
- When the server starts listening, the callback function is executed, and it logs a message to the console.

Once the server is running, it can handle incoming HTTP requests from the frontend and send appropriate responses back.

## HTTP Methods

### GET

The GET method is used to retrieve data from a specified resource on a server. It is a read-only method that does not modify or update any data on the server. In the provided example, an Express server is created using the `express` package. When a GET request is made to the `/students` endpoint, the server responds with a JSON array containing student names. The `res.json('students')` statement sends the response with the string `students` as the data.

**Example:**

```js
import express from 'express';

const app = express();
app.get('/students', (req, res) => {
    res.json('students');
});
app.listen(5000, () => {
    console.log('Listening on port 5000...');
});
```

## POST

The POST method is used to send data to the server to create a new resource or perform an action. It submits data in the body of the request to be processed by the server. In the provided example, when a POST request is made to the `/student` endpoint, the server extracts the `name` and `roll` properties from the request body. Then, it sends a response with a JSON object containing a success status and a message indicating the successful creation of a student with the provided information.

**Example:**

```js
import express from 'express';

const app = express();
app.get('/students', (req, res) => {
    const students = ["Saurabh", "Yogita", "Bandini", "Harshada", "Darshan"];
    res.json(students);
});

app.post('/student', (req, res) => {
    const name = req.body.name;
    const roll = req.body.roll;

    res.json({
        status: 'success',
        message: `Student ${name} created with roll number ${roll}`
    });
});

app.listen(5000, () => {
    console.log('Listening on port 5000');
});
```

## Nodemon 

`Nodemon` is a utility that automatically monitors changes in your source code and restarts the server whenever a change is detected. It is commonly used during development to save time and effort in manually restarting the server after each code modification.

To use nodemon, you need to install it globally using npm by running the following command in your terminal:

```js
npm i nodemon
```

After installing `nodemon`, you can add it to the scripts section of your `package.json` file. The provided example adds a script called `start` to the `package.json` file. The script executes the command `nodemon index.js` when you run `npm start`. This means that `nodemon` will monitor the `index.js` file for changes and automatically restart the server whenever a change is detected.

Here's how the scripts section of your `package.json` file should look like:

```js
"scripts": {
    "start": "nodemon index.js"
}
```

With this setup, you can conveniently start your server using `npm start`, and nodemon will take care of automatically restarting the server whenever you make changes to the code.