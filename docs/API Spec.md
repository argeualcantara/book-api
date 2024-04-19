# Livrello API Specs

Welcome to the documentation of the Book System API. This API allows access to and manipulation of information about books in the system.

## Base URL

```
https://api.livrello.com/v1
```

## Endpoints

### List Books

Endpoint to retrieve a list of all books available in the system.

- **URL:** `/books`
- **Method:** GET
- **Optional query parameters:**
  - `author`: Filter by specific author
  - `category`: Filter by book category
- **Response example:**
  ```json
  [
    {
      "id": 1,
      "title": "The Lord of the Rings",
      "author": "J.R.R. Tolkien",
      "category": "Fantasy"
    },
    {
      "id": 2,
      "title": "1984",
      "author": "George Orwell",
      "category": "Science Fiction"
    }
  ]
  ```

### Book Details

Endpoint to retrieve details of a specific book by its ID.

- **URL:** `/books/{id}`
- **Method:** GET
- **URL parameters:**
  - `id`: Book ID
- **Response example:**
  ```json
  {
    "id": 1,
    "title": "The Lord of the Rings",
    "author": "J.R.R. Tolkien",
    "category": "Fantasy",
    "synopsis": "An epic story about the journey of a group of beings in search of the ultimate fate of the powerful ring.",
    "publication_year": 1954,
    "publisher": "HarperCollins"
  }
  ```

### Add Book

Endpoint to add a new book to the system.

- **URL:** `/books`
- **Method:** POST
- **Request body:**
  ```json
  {
    "title": "New Book",
    "author": "Unknown Author",
    "category": "Other",
    "synopsis": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
    "publication_year": 2024,
    "publisher": "New Publisher"
  }
  ```
- **Response example (success):**
  ```json
  {
    "id": 3,
    "message": "Book added successfully."
  }
  ```

### Update Book

Endpoint to update details of an existing book by its ID.

- **URL:** `/books/{id}`
- **Method:** PUT
- **URL parameters:**
  - `id`: Book ID
- **Request body:**
  ```json
  {
    "title": "New Title",
    "author": "Updated Author",
    "category": "Updated Category"
  }
  ```
- **Response example (success):**
  ```json
  {
    "message": "Book details updated successfully."
  }
  ```

### Remove Book

Endpoint to remove a book from the system by its ID.

- **URL:** `/books/{id}`
- **Method:** DELETE
- **URL parameters:**
  - `id`: Book ID
- **Response example (success):**
  ```json
  {
    "message": "Book removed successfully."
  }
  ```

This is just a basic structure for the API documentation. You can expand and add more details as needed to meet the requirements of your system.
