---
title: Simple To-Do application
type: docs
weight: 4
prev: docs/Back End/3leaf
---

In this guide, we will create a simple Todo application using Node.js and Express.js. This application will implement four APIs: **GET**, **POST**, **PUT**, and **DELETE** to manage Todo items. We will store the data in a JSON file.

## Understanding JSON Storage

**JSON (JavaScript Object Notation)** is a lightweight data interchange format that is easy for humans to read and write, and easy for machines to parse and generate. In our Todo application, we will use a JSON file to store our Todo items as an array of objects, which allows us to easily add, retrieve, update, and delete items.

The JSON file (`todos.json`) will initially look like this:

```json
[]
```

This represents an empty array where our Todo items will be stored.

## Before starting the project lets setup some things
In our Todo application, we will be using the following packages:

1. **express**: A minimal and flexible Node.js web application framework that provides a robust set of features for building web and mobile applications.
2. **body-parser**: Middleware for parsing the body of incoming requests, especially useful for handling JSON data.

## Installation Commands

To install these packages, you can use the following `npm install` commands:

```bash
npm install express body-parser
```

These commands will install both `express` and `body-parser` packages and add them to your `package.json` file as dependencies.

## Building the Todo Application

### Step 1: Create the Server

1. **Set Up Express Server:**
   Create an `index.js` file and set up your Express server:

   ```javascript
   const express = require('express');
   const bodyParser = require('body-parser');
   const fs = require('fs');
   const app = express();
   const port = 3000;

   app.use(bodyParser.json());
   ```

### Step 2: Implement the APIs

#### 1. GET API

This API retrieves all Todo items from the JSON file.

```javascript
app.get('/todos', (req, res) => {
   fs.readFile('todos.json', (err, data) => {
      if (err) {
         return res.status(500).json({ message: 'Error reading data' });
      }
      const todos = JSON.parse(data);
      res.json(todos);
   });
});
```

#### 2. POST API

This API creates a new Todo item.

```javascript
app.post('/todos', (req, res) => {
   const newTodo = req.body;

   fs.readFile('todos.json', (err, data) => {
      if (err) {
         return res.status(500).json({ message: 'Error reading data' });
      }
      const todos = JSON.parse(data);
      todos.push(newTodo);

      fs.writeFile('todos.json', JSON.stringify(todos), (err) => {
         if (err) {
            return res.status(500).json({ message: 'Error saving data' });
         }
         res.status(201).json(newTodo);
      });
   });
});
```

#### 3. PUT API

This API updates an existing Todo item based on its ID.

```javascript
app.put('/todos/:id', (req, res) => {
   const todoId = req.params.id;
   const updatedTodo = req.body;

   fs.readFile('todos.json', (err, data) => {
      if (err) {
         return res.status(500).json({ message: 'Error reading data' });
      }
      let todos = JSON.parse(data);
      todos = todos.map(todo => (todo.id === todoId ? { ...todo, ...updatedTodo } : todo));

      fs.writeFile('todos.json', JSON.stringify(todos), (err) => {
         if (err) {
            return res.status(500).json({ message: 'Error saving data' });
         }
         res.json(updatedTodo);
      });
   });
});
```

#### 4. DELETE API

This API deletes a Todo item based on its ID.

```javascript
app.delete('/todos/:id', (req, res) => {
   const todoId = req.params.id;

   fs.readFile('todos.json', (err, data) => {
      if (err) {
         return res.status(500).json({ message: 'Error reading data' });
      }
      let todos = JSON.parse(data);
      todos = todos.filter(todo => todo.id !== todoId);

      fs.writeFile('todos.json', JSON.stringify(todos), (err) => {
         if (err) {
            return res.status(500).json({ message: 'Error saving data' });
         }
         res.status(204).send();
      });
   });
});
```

### Step 3: Start the Server

Add the following code at the end of your `index.js` file to start the server:

```javascript
app.listen(port, () => {
   console.log(`Server is running at http://localhost:${port}`);
});
```

## Conclusion

You've created a simple Todo application that allows you to manage Todo items using a JSON file for storage. This application demonstrates how to implement RESTful APIs in Node.js and Express.js for creating, reading, updating, and deleting data. You can enhance this application further by adding error handling, data validation, or even a front-end interface.