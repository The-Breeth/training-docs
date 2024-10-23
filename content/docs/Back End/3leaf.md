---
title: Nodemon & npm
type: docs
weight: 3
next: docs/Getting Started/4leaf
prev: docs/Back End/2leaf
---

## What is Nodemon?

Nodemon is a development tool for Node.js applications that automatically restarts your server when it detects file changes. It’s widely used to speed up development by eliminating the need to manually stop and restart the server after every code change.

## What is npm?

npm (Node Package Manager) is the default package manager for Node.js. It helps you manage dependencies (libraries or modules) in your Node.js project. It allows you to install, update, and manage the various packages and tools that you need in your development environment.

### Key Features of npm:
- **Dependency Management**: You can install libraries and tools (like Nodemon) into your project.
- **Global and Local Installation**: You can install packages either globally (for use across projects) or locally (for use in a specific project).
- **Script Management**: You can create and run custom scripts for tasks like starting your application or running tests.

## How to Install Dependencies Using npm

### Step 1: Initialize a Project with npm

**Note:**
We already did this step in [Node.js & Express.js](training-docs/docs/back-end/2leaf) documentation. If you haven't done it yet, please go back and follow the document to complete the necessary setup before proceeding.


Before installing any dependencies, you need to initialize a new Node.js project. This creates a `package.json` file to manage your project settings and dependencies:

```bash
npm init -y
```

The `-y` flag automatically sets up the `package.json` file with default options.

### Step 2: Install a Dependency

To install a dependency, use the following command:

```bash
npm install <package-name>
```

For example, to install Nodemon as a development dependency:

```bash
npm install --save-dev nodemon
```

- **`--save-dev`** installs the package as a development dependency, meaning it is only required during development (not in production).
- Without `--save-dev`, the package will be installed as a regular dependency for both development and production use.

Once installed, the dependencies are saved in the `node_modules` folder and referenced in the `package.json` file.

### Step 3: Running npm Scripts

You can define and run custom scripts using npm. In the `package.json` file, under the `scripts` section, you can add scripts like starting your server with Nodemon:

```json
"scripts": {
  "start": "node index.js",
  "dev": "nodemon index.js"
}
```

To run these scripts, you would use the following commands:

- For starting the server using Node.js:

  ```bash
  npm run start
  ```

- For starting the server in development mode with Nodemon:

  ```bash
  npm run dev
  ```

## Using Nodemon

Once Nodemon is installed, it will automatically restart your server when you save changes to your code. To use Nodemon, simply replace `node` with `nodemon` when running your application.

### Example

Instead of running:

```bash
node index.js
```

Run:

```bash
nodemon index.js
```

This will start your application with Nodemon. When you make changes to your files, Nodemon will automatically detect them and restart the server.

### Global Installation of Nodemon

You can also install Nodemon globally so that it can be used in any Node.js project:

```bash
npm install -g nodemon
```

With this global installation, you can use `nodemon` in any directory without needing to install it locally in each project.

## Benefits of Using npm and Nodemon

- **Efficient Dependency Management**: npm makes it easy to manage and install project dependencies. You can control which packages are installed for development or production.
- **Automated Server Restarts**: Nodemon streamlines the development process by automatically restarting your application whenever code changes are detected.
- **Script Automation**: npm allows you to define scripts, making it easier to manage tasks like starting your server, running tests, and building your project.

## Conclusion

Nodemon, combined with npm, offers a powerful and flexible development environment for Node.js applications. npm allows you to easily install and manage packages like Nodemon, while Nodemon saves time by automating the process of restarting your server as you develop your application.