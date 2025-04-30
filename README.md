# YuedLeaw Project

<div align="center">
  <img src="images/LOGO.png" alt="Logo" width="200" height="200">
  <h3>YuedLeaw Project</h3>
  <p>Premium T-shirt Design & Customization Platform</p>
</div>

## Table of Contents
- [About The Project](#about-the-project)
- [Prerequisites](#prerequisites)
  - [Installing Node.js](#installing-nodejs)
- [Installation](#installation)
  - [1. Database Setup](#1-database-setup)
  - [2. Frontend Setup](#2-frontend-setup)
  - [3. Backend Setup](#3-backend-setup)
- [Starting the Application](#starting-the-application)
- [Accessing the Website](#accessing-the-website)

## About The Project

YuedLaew is a Thai-based e-commerce platform specializing in high-quality, personalized T-shirt designs. Our platform offers:

- A vast selection of stylish, trendy, and culturally relevant pre-made designs
- Custom T-shirt creation where customers can upload their own images
- Size and color customization options
- Premium quality materials, efficient printing, and reliable shipping

## Prerequisites

Before beginning installation, ensure you have:

- **Node.js** installed (see installation instructions below)
- **MySQL** installed and running
- **Visual Studio Code** or another code editor

### Installing Node.js

1. Check if Node.js is already installed:
   ```bash
   node --version
   ```
   If it shows a version number, you can skip to the next section.

2. If Node.js is not installed, we recommend using NVM (Node Version Manager):

   **For Windows:**
   - Download the NVM for Windows installer from [GitHub](https://github.com/coreybutler/nvm-windows/releases)
   - Run the installer and follow the prompts
   - Open a new Command Prompt and install Node.js:
     ```bash
     nvm install 18.16.0
     nvm use 18.16.0
     ```

   **For macOS/Linux:**
   - Install NVM using curl:
     ```bash
     curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
     ```
   - Or using wget:
     ```bash
     wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
     ```
   - Close and reopen your terminal, then install Node.js:
     ```bash
     nvm install 18.16.0
     nvm use 18.16.0
     ```

3. Verify the installation:
   ```bash
   node --version
   npm --version
   ```

## Installation

### 1. Database Setup

1. Navigate to the 'Database' folder from the GitHub repository
2. Download both `YuedLeaw_db.sql` and `YuedLeaw_info.sql` files
3. Open MySQL and execute the following:
   
   a. Run `YuedLeaw_db.sql` script to create the database structure:
   ```sql
   SOURCE path/to/YuedLeaw_db.sql;
   ```
   
   b. Run `YuedLeaw_info.sql` to populate the database with initial data:
   ```sql
   SOURCE path/to/YuedLeaw_info.sql;
   ```
   
   c. Create a database user with appropriate permissions:
   ```sql
   CREATE USER 'yuedleaw'@'%' IDENTIFIED BY 'yuedleaw888';
   GRANT ALL ON YuedLeaw_db.* TO 'yuedleaw';
   FLUSH PRIVILEGES;
   ```

### 2. Frontend Setup

1. Create a new folder named `WebDev--frontend`
2. From the 'Frontend' folder in the repository, download:
   - `app.js`
   - `html.zip`
3. Place `app.js` in your `WebDev--frontend` folder
4. Extract `html.zip` into the same folder
5. Open the folder in Visual Studio Code
6. Initialize the Node.js project:
   ```bash
   npm init
   ```
   - Set entry point to: `app.js`
   - Author: `yuedleaw` (or your name)
   - Confirm with `yes`
7. Install required dependencies:
   ```bash
   npm install express nodemon path router
   ```
8. Update the `package.json` file to include the start script:
   ```json
   {
     "name": "webdev--frontend",
     "version": "1.0.0",
     "main": "app.js",
     "scripts": {
       "start": "nodemon app.js"
     },
     "author": "yuedleaw",
     "license": "ISC",
     "description": "",
     "dependencies": {
       "express": "^5.1.0",
       "nodemon": "^3.1.9",
       "path": "^0.12.7",
       "router": "^2.2.0"
     }
   }
   ```

### 3. Backend Setup

1. Create a new folder named `WebDev--backend`
2. From the 'Backend' folder in the repository, download:
   - `backend.js`
   - `images.zip`
3. Place `backend.js` in your `WebDev--backend` folder
4. Extract `images.zip` into the same folder
5. Open the folder in a new Visual Studio Code window
6. Initialize the Node.js project:
   ```bash
   npm init
   ```
   - Set entry point to: `backend.js`
   - Author: `yuedleaw` (or your name)
   - Confirm with `yes`
7. Install required dependencies:
   ```bash
   npm install express nodemon cors dotenv mysql2 fs multer
   ```
8. Update the `package.json` file to include the start script:
   ```json
   {
     "name": "webdev--backend",
     "version": "1.0.0",
     "main": "backend.js",
     "scripts": {
       "start": "nodemon backend.js"
     },
     "author": "yuedleaw",
     "license": "ISC",
     "description": "",
     "dependencies": {
       "cors": "^2.8.5",
       "dotenv": "^16.5.0",
       "express": "^5.1.0",
       "fs": "^0.0.1-security",
       "multer": "^1.4.5-lts.2",
       "mysql2": "^3.14.0",
       "nodemon": "^3.1.9"
     }
   }
   ```
9. Create a `.env` file in the backend folder with the following content:
   ```
   PORT = 3100
   
   DB_HOST = localhost
   DB_USERNAME = yuedleaw
   DB_PASSWORD = yuedleaw888
   DB_DATABASE = YuedLeaw_db
   ```

## Starting the Application

1. Start the Frontend server:
   - Open the `WebDev--frontend` folder in VS Code
   - Run `npm start` in the terminal
   - Verify successful startup with message:
     ```
     [nodemon] starting `node app.js`
     Front-end server listening on port: 3030
     ```

2. Start the Backend server:
   - Open the `WebDev--backend` folder in VS Code
   - Run `npm start` in the terminal
   - Verify successful startup with message:
     ```
     [nodemon] starting `node backend.js`
     Back-end server listening on port: 3100
     API accessible at http://localhost:3100/api
     Connected to DB: YuedLeaw_db
     ```

## Accessing the Website

Once both servers are running, access the YuedLeaw website by navigating to:

**[http://localhost:3030](http://localhost:3030)**

Ensure no other services are using port 3030 or 3100 before starting the application.

# Welcome to YuedLeaw!
