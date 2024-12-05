# Nestjs and MySQL with TypeORM

<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

## Introduction

This project is a backend application developed with NestJS that interacts with a MySQL database. The application provides endpoints to manage users and their profiles, as well as posts associated with the users. The project uses TypeORM for database management and follows the MVC architectural pattern.

## 🔬 Project Structure

### Main Files

- **main.ts**: The entry point of the application. Initializes and starts the NestJS server.

- **app.module.ts**: The main module that imports other modules and configures the database connection.

- **users.module.ts**, **posts.module.ts**: Modules containing functionalities related to users and posts, respectively.

- **users.service.ts**, **posts.service.ts**: Services that handle the business logic.

- **users.controller.ts**, **posts.controller.ts**: Controllers that define the API endpoints.

- **entities**: Directory containing the database entities (User, Profile, Post).

## 🔨 Installation and Configuration

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/nestjs-mysql.git
cd nestjs-mysql
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure the Database

Ensure you have MySQL installed and configured. The database credentials are located in **app.module.ts**. Make sure to adjust them according to your configuration.

### 4. Run the Application

Development Mode

```bash
npm run start:dev
```

This will start the server in development mode at http://localhost:3000/.

## 🚀 API Endpoints

## **Users**

### **Get All Users**

- **Endpoint**: `GET /users`

- **Description**: Retrieves a list of all users along with their posts and profiles.

- **Response**: Array of `User` objects.

### **Get User by ID**

- **Endpoint**: `GET /users/:id`

- **Description**: Retrieves a specific user by their ID along with their posts.

- **Parameters**:

  - **`id`**: User ID (number).

- **Response**: `User` object.

### **Create a User**

- **Endpoint**: `POST /users`

- **Description**: Creates a new user.

- **Request Body**:

  - **`username`**: Username (string).

  - **`password`**: Password (string).

- **Response**: Newly created `User` object.

### **Delete a User**

- **Endpoint**: `DELETE /users/:id`

- **Description**: Deletes a user by their ID.

- **Parameters**:

  - **`id`**: User ID (number).

- **Response**: Object indicating the success of the operation.

### **Update a User**

- **Endpoint**: PATCH /users/:id

- **Description**: Updates a user by their ID.

- **Parameters**:

  - **`id`**: User ID (number).

- **Request Body**:

  - **`username`**: New username (optional, string).

  - **`password`**: New password (optional, string).

- **Response**: Updated `User` object.

### **Create User Profile**

- **Endpoint**: `POST /users/:id/profile`

- **Description**: Creates a profile for a user by their ID.

- **Parameters**:

  - **`id`**: User ID (number).

- **Request Body**:

  - **`firstname`**: First name (string).

  - **`lastname`**: Last name (string).

  - **`age`**: Age (optional, number).

- **Response**: Updated `User` object with the added profile.

## **Posts**

### **Create a Post**

- **Endpoint**: `POST /posts`

- **Description**: Creates a new post associated with a user.

- **Request Body**:

  - **`title`**: Post title (string).

  - **`content`**: Post content (string).

  - **`authorId`**: Author ID (number).

- **Response**: Newly created **Post** object.

### **Get All Posts**

- **Endpoint**: `GET /posts`

- **Description**: Retrieves a list of all posts along with their authors.

- **Response**: Array of `Post` objects.
