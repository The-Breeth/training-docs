---
title: Nodejs & Expressjs
type: docs
weight: 2
next: docs/Getting Started/3leaf
prev: docs/Back End/1leaf
---

## What is Node.js?
Node.js is a runtime environment that allows you to run JavaScript on the server side. It is built on Chrome's V8 JavaScript engine and is commonly used to create back-end services such as APIs.

## What is Express.js?
Express.js is a lightweight web framework for Node.js. It simplifies the process of building web applications and APIs by providing robust routing and middleware features.

### Example: Basic Express Server

Below is a simple Express.js application that listens for HTTP GET requests on the root route (`/`) and responds with "Hello, World!".

```javascript
// index.js
const express = require('express');
const app = express();
const PORT = 3000;

app.get('/', (req, res) => {
    res.send('Hello, World!');
});

app.listen(PORT, () => {
    console.log(`Server is running on http://localhost:${PORT}`);
});
```

# How to Run

1. **Install Node.js**
   Download and install Node.js from [here](https://nodejs.org/).

2. **Initialize a Project**
   Open your terminal and navigate to your project folder. Initialize the project by running the following command:

   ```bash
   npm init -y
   ```
   it should look like this

  ```json
   {
    "name": "training",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1"
    },
    "keywords": [],
    "author": "",
    "license": "ISC"
    }
  ```

3. **Install Express**
   Install the Express framework by running the following command:

   ```bash
   npm install express
   ```

4. **Run the Application**
   Create a file named `index.js` with the following code:

   ```javascript
   const express = require('express');
   const app = express();

   app.get('/', (req, res) => {
       res.send('Hello, World!');
   });

   app.listen(3000, () => {
       console.log('Server is running on http://localhost:3000');
   });
   ```

   Then, run the application using:

   ```bash
   node index.js
   ```

5. **View in Browser**
   Open your browser and go to [http://localhost:3000](http://localhost:3000). You should see "Hello, World!" displayed.