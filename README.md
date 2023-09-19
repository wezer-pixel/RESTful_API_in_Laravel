# Book Management API

Welcome to the Book Management API! This API allows you to manage a collection of books, including operations like viewing all books, accessing a single book, updating, creating, and deleting books. The API is built using the Laravel framework and follows RESTful principles for seamless interaction.

## Table of Contents

1. [API Endpoints](#api-endpoints)
   - [Get All Books](#get-all-books)
   - [Get a Single Book](#get-a-single-book)
   - [Create a Book](#create-a-book)
   - [Update a Book](#update-a-book)
   - [Delete a Book](#delete-a-book)
   
2. [Request and Response Examples](#request-and-response-examples)

3. [Setup and Usage](#setup-and-usage)

4. [Testing](#testing)

## API Endpoints

### Get All Books

**Endpoint:** `GET /api/books`

This endpoint retrieves a list of all books available in the database.

### Get a Single Book

**Endpoint:** `GET /api/books/{id}`

This endpoint retrieves details of a single book identified by its unique `id`.

### Create a Book

**Endpoint:** `POST /api/books`

This endpoint allows you to create a new book by providing the book details in the request body.

**Request Body:**
```json
{
  "name": "Book Title",
  "author": "Author Name",
  "publish_date": "YYYY-MM-DD"
}
```

### Update a Book

**Endpoint:** `PUT /api/books/{id}`

This endpoint allows you to update the details of an existing book identified by its unique `id`.

**Request Body:**
```json
{
  "name": "Updated Book Title",
  "author": "Updated Author Name",
  "publish_date": "YYYY-MM-DD"
}
```

### Delete a Book

**Endpoint:** `DELETE /api/books/{id}`

This endpoint allows you to delete a book based on its unique `id`.

## Request and Response Examples

### Example 1: Get All Books

**Request:**
```
GET /api/books
```

**Response:**
```json
[
  {
    "id": 1,
    "name": "Book 1",
    "author": "Author A",
    "publish_date": "2023-09-15"
  },
  {
    "id": 2,
    "name": "Book 2",
    "author": "Author B",
    "publish_date": "2023-08-20"
  }
]
```

### Example 2: Create a Book

**Request:**
```
POST /api/books
```

**Request Body:**
```json
{
  "name": "New Book",
  "author": "New Author",
  "publish_date": "2023-10-10"
}
```

**Response:**
```json
{
  "id": 3,
  "name": "New Book",
  "author": "New Author",
  "publish_date": "2023-10-10"
}
```

## Setup and Usage

1. Clone this repository to your local machine.

2. Install dependencies using Composer:
   ```
   composer install
   ```

3. Configure your database settings in the `.env` file.

4. Run database migrations to set up the required tables:
   ```
   php artisan migrate
   ```

5. Run database seeder to set populate the table:
   ```
   php artisan db:seed --class=BookSeeder
   ```


6. Start the Laravel development server:
   ```
   php artisan serve
   ```

7. You can now use Postman or any API testing tool to interact with the API at `http://127.0.0.1:8000/api`.

## Testing

To run the API tests, use the following command:
```
php artisan test
```

This will execute the test suite and provide feedback on the functionality and integrity of the API.
