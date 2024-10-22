---
title: Back End
type: docs
weight: 3
next: docs/Back End/1leaf
prev: docs/Getting Started/1leaf
sidebar:
  open: false
---

### Backend Project Overview

This backend project is structured for a Node.js application using Express. It includes various directories and files organized to facilitate development, maintainability, and scalability.

#### Tech Stack
- **Node.js**: Runtime environment for executing JavaScript on the server side.
- **Express**: Web framework for building APIs and handling HTTP requests.
- **Babel**: JavaScript compiler that allows the use of modern JavaScript features.
- **Joi**: For data validation.
- **Multer**: Middleware for handling multipart/form-data, primarily for file uploads.
- **Helmet**: For securing Express apps by setting various HTTP headers.
- **CORS**: Middleware for enabling Cross-Origin Resource Sharing.
- **dotenv**: For managing environment variables.

### Folder Structure

```plaintext
└── 📁be-project
    └── 📁app
        └── index.js
        └── server.js
    └── 📁Config
        └── global.js
        └── index.js
        └── local.js
    └── 📁Constants
        └── constant.js
        └── errors.js
        └── index.js
    └── 📁Controllers
        └── index.js
        └── test.js
    └── 📁Middlewares
        └── index.js
        └── jwtVerification.js
    └── 📁Routes
        └── index.js
        └── test.js
    └── 📁Services
        └── index.js
        └── mongoService.js
    └── 📁Utils
        └── asyncWrapper.js
        └── commonFunctions.js
        └── crypt.js
        └── index.js
        └── logger.js
        └── multer.js
    └── 📁Validations
        └── index.js
        └── utils.js
    └── .babelrc
    └── .eslintignore
    └── .eslintrc
    └── .gitignore
    └── LICENSE
    └── package-lock.json
    └── package.json
    └── server.js
```

### Key Directories

1. **📁app**
   - Contains the main application files, including `index.js` for app initialization and `server.js` for starting the server.

2. **📁Config**
   - Configuration files for different environments: `global.js` for global configurations, `local.js` for local settings, and `index.js` for aggregating configurations.

3. **📁Constants**
   - Stores constant values used throughout the application, including error messages and other static values in `constant.js` and `errors.js`.

4. **📁Controllers**
   - Business logic for handling requests, including the main controller in `index.js` and specific functionality in `test.js`.

5. **📁Middlewares**
   - Contains middleware functions, including `jwtVerification.js` for validating JSON Web Tokens.

6. **📁Routes**
   - Defines the application's routes, aggregating routes in `index.js` and specific routes in `test.js`.

7. **📁Services**
   - Contains service logic for data handling, with `mongoService.js` managing interactions with MongoDB.

8. **📁Utils**
   - Utility functions and helpers, including logging (`logger.js`), async wrappers (`asyncWrapper.js`), and encryption (`crypt.js`).

9. **📁Validations**
   - Validation logic for incoming requests, with specific functions in `utils.js`.

10. **Root Files**
    - Configuration files for Babel, ESLint, and other tools, along with essential project files such as `package.json` and `LICENSE`.

### Scripts in `package.json`

- **start**: Runs the application using Babel Node.
- **dev**: Starts the application in development mode using Nodemon, which automatically restarts the server on file changes.
- **build**: Cleans the `dist` directory, compiles the source files to `dist`, and copies `package.json` to `dist`.
- **serve**: Runs the built application from the `dist` directory.

### Dependencies
- **express**: Web framework for Node.js.
- **joi**: Validation library for data.
- **multer**: Middleware for handling file uploads.
- **helmet**: Middleware for security headers.
- **dotenv**: Environment variable management.
- **cors**: Middleware for handling CORS.
- **@babel/**: Babel packages for transpiling modern JavaScript.

### References

- [Node.js Documentation](https://nodejs.org/en/docs/)
- [Express Documentation](https://expressjs.com/)
- [Babel Documentation](https://babeljs.io/docs/en/)
- [Joi Documentation](https://joi.dev/api/)
- [Multer Documentation](https://www.npmjs.com/package/multer)
- [Helmet Documentation](https://helmetjs.github.io/)
- [CORS Documentation](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [dotenv Documentation](https://www.npmjs.com/package/dotenv)
- [Nodemon Documentation](https://nodemon.io/)
- [ESLint Documentation](https://eslint.org/docs/user-guide/getting-started)