## **Essential Package JSON Scripts for Node.js Projects**

In Node.js, defining scripts in package.json simplifies project workflows. Here are essential scripts every developer should know:

**Common Scripts**

- start: Launches the server or application.
- test: Executes test cases for your project.
- build: Compiles and prepares production-ready code.
- dev: Starts a development server with live reload or debugging.
- lint: Enforces code style guidelines by running a linter.

**Additional Scripts**:

- clean: Removes build artifacts or temporary files.
- deploy: Deploys the application to a server or cloud.

Example package.json Scripts:

```plaintext
{
  "scripts": {
    "start": "node app.js",
    "dev": "nodemon app.js",
    "test": "jest",
    "build": "webpack --mode production",
    "lint": "eslint .",
    "clean": "rm -rf dist/",
    "deploy": "scp -r dist/ user@server:/var/www/project"
  }
}
```

**How to Pass Arguments:**

- Add -- after the script name in the terminal, followed by the arguments or flags.
- Access these arguments using process.argv in your Node.js scripts.