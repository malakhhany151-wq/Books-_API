# Books API

A simple API built with PHP and MySQL to manage book records. It uses PDO for database operations and JSON for exchanging data between the client and server.

## Features

- **GET:** Retrieve all books, ordered by ID in descending order.
- **POST:** Add a new book using JSON request data.
- **DELETE:** Delete a book by its ID.
- **Input Validation:** Check required fields when creating a book.
- **HTTP Status Codes:** Return appropriate status codes for successful requests and common errors.
- **Error Handling:** Handle database exceptions and unsupported HTTP methods.

## Technologies Used

- PHP
- MySQL
- PDO
- JSON
- HTTP Methods

## Database Setup

1. Create a MySQL database named `Library`.
2. Create a table named `books` with the following columns:

| Column | Type | Description |
|---|---|---|
| `id` | INT, AUTO_INCREMENT, PRIMARY KEY | Unique book ID |
| `title` | VARCHAR(255) | Book title |
| `author` | VARCHAR(255) | Book author |
| `price` | DECIMAL(10,2) | Book price |

## Installation and Setup

1. Install and open XAMPP.
2. Start Apache and MySQL.
3. Place the project folder inside the `htdocs` directory.
4. Create the `Library` database and the `books` table.
5. Configure the PDO database connection directly in `books_api.php` using your local MySQL credentials.
6. Open the API using the following URL:

`http://localhost/BooksAPI/books_api.php`

Replace `BooksAPI` with your actual project folder name if it is different.

## API Endpoints

### 1. Get All Books

**Method:** `GET`

**URL:**

`http://localhost/BooksAPI/books_api.php`

Returns all books stored in the database as JSON.

### 2. Add a New Book

**Method:** `POST`

**URL:**

`http://localhost/BooksAPI/books_api.php`

Send the book data as JSON in the request body:

```json
{
  "title": "PHP Basics",
  "author": "Ahmed",
  "price": 150
}
```

The request requires `title`, `author`, and `price`.

### 3. Delete a Book

**Method:** `DELETE`

**URL:**

`http://localhost/BooksAPI/books_api.php?id=1`

Replace `1` with the ID of the book you want to delete.

## HTTP Status Codes

| Status Code | Meaning |
|---|---|
| `200 OK` | Request completed successfully |
| `201 Created` | Book created successfully |
| `400 Bad Request` | Required data or ID is missing |
| `404 Not Found` | Book does not exist |
| `405 Method Not Allowed` | Unsupported HTTP method |
| `500 Internal Server Error` | Server-side or database error |

## Project Structure

```text
Books-API/
├── books_api.php
├── database.sql
└── README.md
```

## Learning Objectives

This project demonstrates practical use of PHP, PDO, MySQL, JSON request handling, HTTP methods, input validation, and basic API error handling.

## Security Note

Do not upload real database passwords or sensitive credentials to a public repository. Keep local credentials secure and configure them appropriately before running the project.

