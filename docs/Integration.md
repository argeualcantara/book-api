# Livrello API Integration

This documentation provides guidance on integrating the Livrello API into your application for managing book-related functionalities.

## API Base URL

The base URL for accessing the Livrello API endpoints is:

```
https://api.livrello.com/v1
```

## Authentication

The Livrello API does not require authentication for accessing book-related functionalities. All endpoints are publicly accessible.

## API Endpoints

### 1. List Books

- **URL:** `/books`
- **Method:** GET
- **Description:** Retrieves a list of all books available in the system.
- **Response:** Array of book objects including ID, title, author, category, and other details.

### 2. Get Book Details

- **URL:** `/books/{id}`
- **Method:** GET
- **Description:** Retrieves details of a specific book by its ID.
- **Parameters:** `{id}` - ID of the book.
- **Response:** Book object containing details such as title, author, category, synopsis, publication year, and publisher.

### 3. Add Book

- **URL:** `/books`
- **Method:** POST
- **Description:** Adds a new book to the system.
- **Request Body:** JSON object containing book details such as title, author, category, synopsis, publication year, and publisher.
- **Response:** ID of the newly added book and success message.

### 4. Update Book

- **URL:** `/books/{id}`
- **Method:** PUT
- **Description:** Updates details of an existing book by its ID.
- **Parameters:** `{id}` - ID of the book.
- **Request Body:** JSON object containing updated book details (title, author, category, etc.).
- **Response:** Success message indicating that the book details have been updated.

### 5. Delete Book

- **URL:** `/books/{id}`
- **Method:** DELETE
- **Description:** Deletes a book from the system by its ID.
- **Parameters:** `{id}` - ID of the book.
- **Response:** Success message indicating that the book has been deleted.

## Error Handling

The Livrello API returns appropriate HTTP status codes along with error messages in case of errors. Handle these errors in your application accordingly.

## Example Integration

Below is an example of how to integrate the Livrello API using JavaScript Fetch API:

```javascript
const apiUrl = 'https://api.livrello.com/v1';

// Function to list all books
async function listBooks() {
  const response = await fetch(`${apiUrl}/books`);
  if (!response.ok) {
    throw new Error('Failed to retrieve books');
  }
  return response.json();
}

// Example usage
listBooks()
  .then(books => {
    console.log('List of books:', books);
    // Process the list of books
  })
  .catch(error => {
    console.error('Error:', error.message);
  });
```

## Conclusion

This documentation provides the necessary information to integrate the Livrello API into your application. Follow the guidelines and examples provided to ensure successful integration and efficient management of book-related functionalities.
