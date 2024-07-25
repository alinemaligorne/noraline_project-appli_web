# Node.js API Setup Guide

This guide provides detailed steps to set up a basic Node.js API using Express, Body-Parser, and CORS.

## Step 1: Set Up Your Project

1. **Navigate to the Project Directory**:
    Open your terminal and navigate to your `back-end` directory:
    ```sh
    cd back-end
    ```

2. **Initialize npm**:
    Initialize a new Node.js project with default settings by running:
    ```sh
    npm init -y
    ```
    This command will create a `package.json` file in your `back-end` directory.

## Step 2: Install Required Packages

1. **Install Express, Body-Parser, and CORS**:
    Install the necessary packages for building the API:
    ```sh
    npm install express body-parser cors
    ```

    - **Express**: A minimal and flexible Node.js web application framework that provides a robust set of features to develop web and mobile applications.
    - **Body-Parser**: Middleware to handle parsing of request bodies, making it easier to read data sent in HTTP requests.
    - **Cors**: Middleware to enable Cross-Origin Resource Sharing, allowing your API to be accessed from different origins (domains).

2. **Verify Installation**:
    After the installation is complete, verify that the packages are listed under the `dependencies` section in your `package.json` file:
    ```json
    {
      "name": "back-end",
      "version": "1.0.0",
      "description": "",
      "main": "index.js",
      "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1"
      },
      "keywords": [],
      "author": "",
      "license": "ISC",
      "dependencies": {
        "body-parser": "^1.19.0",
        "cors": "^2.8.5",
        "express": "^4.17.1"
      }
    }
    ```

## Step 3: Set Up Express Server

1. **Create the Entry Point File**:
    Create a file named `index.js` in your `back-end` directory:
    ```sh
    touch index.js
    ```

2. **Set Up Basic Express Server**:
    Open `index.js` in your preferred code editor and add the following code:

    ```javascript
    // Import required packages
    const express = require('express');
    const bodyParser = require('body-parser');
    const cors = require('cors');

    // Create an instance of Express
    const app = express();

    // Define the port number
    const port = 3000;

    // Use CORS middleware to allow cross-origin requests
    app.use(cors());

    // Use Body-Parser middleware to parse JSON and urlencoded request bodies
    app.use(bodyParser.json());
    app.use(bodyParser.urlencoded({ extended: true }));

    // Define a simple route
    app.get('/', (req, res) => {
        res.send('Hello World!');
    });

    // Start the server and listen on the specified port
    app.listen(port, () => {
        console.log(`Server is running on port ${port}`);
    });
    ```

3. **Run the Server**:
    Start the server by running the following command in your terminal:
    ```sh
    node index.js
    ```

4. **Test the Server**:
    Open your web browser and navigate to `http://localhost:3000` or use the following `curl` command in your terminal to test the server:
    ```sh
    curl http://localhost:3000
    ```

    You should see the message "Hello World!".

---

By following these steps, you will have a basic Node.js server running with Express, Body-Parser, and CORS configured. You can now proceed to define additional routes and functionality for your API.
