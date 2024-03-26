# BackendWithJavascript
![image](https://github.com/Asifekhlaque/BackendWithJavascript/assets/132199879/ba3f4ba5-cb0b-4fa3-a7e5-43089bce97fe)

### What is Node.js?
Node.js is a powerful tool that lets you run JavaScript outside of web browsers, on your computer or server.

### Characteristics:
1. **Lightweight**: Node.js is built on Chrome's V8 JavaScript engine, making it fast and efficient.
2. **Event-Driven**: It uses an event-driven, non-blocking I/O model, which means it can handle many connections simultaneously without getting stuck.
3. **Cross-Platform**: It runs on various platforms like Windows, macOS, and Linux, making it versatile.
4. **Scalable**: Node.js applications can handle a large number of simultaneous connections, making them suitable for high-traffic websites and applications.

### Key Features:
1. **NPM (Node Package Manager)**: Node.js comes with NPM, a package manager that lets you easily install, manage, and share reusable code packages.
2. **Asynchronous I/O**: Node.js uses asynchronous programming, allowing it to handle multiple requests without waiting for each one to finish.
3. **Single Programming Language**: With Node.js, you can use JavaScript for both client-side and server-side development, reducing the need to switch between languages.
4. **Vast Ecosystem**: Node.js has a vast ecosystem of libraries and frameworks, providing developers with numerous tools to build various types of applications.

### Use Cases:
1. **Web Servers**: Node.js is commonly used to build fast and scalable web servers. Popular frameworks like Express.js make it easy to create robust server-side applications.
2. **API Development**: It's great for building APIs (Application Programming Interfaces) to handle communication between different software systems.
3. **Real-time Applications**: Node.js excels at building real-time applications like chat applications, online gaming platforms, and collaborative tools.
4. **Microservices Architecture**: Node.js is well-suited for building microservices, allowing developers to create modular, scalable, and maintainable systems.

### To see if Node is installed and fo check the version of you are Node JS
Windows + R -> CMD 
```
node -v
```
![image](https://github.com/Asifekhlaque/BackendWithJavascript/assets/132199879/93211896-7325-4d65-bf29-dbe0d0aa3d91)


### What is `package.json`?

At its core, `package.json` is a JSON (JavaScript Object Notation) file that resides in the root directory of a Node.js project. It primarily serves three main purposes:

1. **Metadata**: It contains metadata about the project such as its name, version, description, author, license, etc.
   
2. **Dependencies**: It lists the project's dependencies, both runtime and development, along with their respective versions. This enables others to install the same dependencies and ensures consistency across environments.

3. **Scripts**: It defines custom scripts that can be executed via npm (Node Package Manager). These scripts can be used for various tasks such as running tests, building the project, starting a development server, etc.

### Anatomy of `package.json`

A typical `package.json` file consists of several key fields:

```json
{
  "name": "your-project-name",
  "version": "1.0.0",
  "description": "Brief description of your project",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "test": "jest"
  },
  "keywords": ["keyword1", "keyword2"],
  "author": "Your Name",
  "license": "MIT",
  "dependencies": {
    "dependency1": "^1.0.0",
    "dependency2": "^2.1.0"
  },
  "devDependencies": {
    "devDependency1": "^1.0.0",
    "devDependency2": "^2.1.0"
  }
}
```

### Utilizing `package.json` 

1. **Project Description**: Include a brief overview of your project, which can be extracted from the `description` field in your `package.json`. This provides readers with an immediate understanding of what your project aims to achieve.

2. **Installation Instructions**: Use the `dependencies` and `devDependencies` sections to guide users on how to install the required dependencies. You can provide a command like `npm install` to automatically install all dependencies listed in `package.json`.

3. **Usage**: If your project includes scripts defined in `package.json`, such as `start`, `test`, or custom scripts, document them in your README. This helps users understand how to interact with your project.

4. **Contributing Guidelines**: Mention the preferred process for contributing to your project. This might involve forking the repository, installing dependencies, running tests, making changes, and submitting pull requests. You can refer to the `scripts` section for commands related to testing and building.

5. **License Information**: Include details about the project's license, extracted from the `license` field in `package.json`. This informs users about the terms under which they can use, modify, and distribute your project.

![image](https://github.com/Asifekhlaque/BackendWithJavascript/assets/132199879/743975d3-061a-4f8b-b7af-8ed8cf5000f7)
### how to import nodemon globally
```
npm install -g nodemon
```
### To verify that nodemon has been installed globally, run the following command:
```
nodemon -v
```
### How to run nodemon with your project
```
nodemon projectname.js
```
### Basic Node js code for server hosting
#### Common Js
```js
const { createServer } = require('node:http');
const hostname = '127.0.0.1';
const port = 3000;
const server = createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World');
});
server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```
#### ES6 moodel
```js
import http from 'http';
const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res)  => {
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end('Node bro kaha ho bhai ma nodemon banaya hai\n');
});

server.listen(port, hostname, () =>  { 
    console.log(`Server running at http://${hostname}:${port}/`);
});
```
![image](https://github.com/Asifekhlaque/BackendWithJavascript/assets/132199879/ce990750-ef07-4ed8-a37b-5807b41568c3)

# Express.js Fundamentals

This repository covers the fundamentals of Express.js, a popular Node.js framework for building web applications and APIs.

## Table of Contents

1. [Introduction to Express.js](#introduction-to-expressjs)
2. [Installation](#installation)
3. [Getting Started](#getting-started)
4. [Routing](#routing)
5. [Middleware](#middleware)
6. [Error Handling](#error-handling)
7. [Static Files](#static-files)
8. [Template Engines](#template-engines)
9. [Database Integration](#database-integration)
10. [Authentication and Authorization](#authentication-and-authorization)
11. [Testing](#testing)
12. [Deployment](#deployment)
13. [Resources](#resources)

## Introduction to Express.js

Express.js is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications. It facilitates the development of web servers, APIs, and web applications quickly and efficiently.

## Installation

You can install Express.js via npm:

```bash
npm install express
```

## Getting Started

To create a basic Express.js server:

```javascript
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(port, () => {
  console.log(`Server is listening at http://localhost:${port}`);
});
```

## Routing

Express provides a simple and intuitive way to define routes for handling different HTTP requests.

```javascript
app.get('/users', (req, res) => {
  // Handle GET request for /users
});

app.post('/users', (req, res) => {
  // Handle POST request for /users
});
```

## Middleware

Middleware functions are functions that have access to the request object (`req`), the response object (`res`), and the next middleware function in the application’s request-response cycle.

```javascript
app.use(express.json()); // Parse incoming request bodies in JSON format
```

## Error Handling

Express provides error-handling middleware to centralize error handling.

```javascript
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});
```

## Static Files

Serve static files such as images, CSS, JavaScript files, etc., using the `express.static` middleware.

```javascript
app.use(express.static('public'));
```

## Template Engines

Integrate template engines like EJS, Pug, Handlebars, etc., to generate dynamic HTML content.

```javascript
app.set('view engine', 'ejs');
```

## Database Integration

Express.js can be integrated with various databases such as MongoDB, MySQL, PostgreSQL, etc., using appropriate libraries.

## Authentication and Authorization

Implement user authentication and authorization using middleware like Passport.js.

## Testing

Utilize testing frameworks like Mocha, Chai, Supertest, etc., for testing Express applications.

## Deployment

Deploy Express.js applications on platforms like Heroku, AWS, Azure, etc.

## Resources

- [Express.js Documentation](https://expressjs.com/)
- [Express.js GitHub Repository](https://github.com/expressjs/express)

