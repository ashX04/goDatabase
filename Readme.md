
# Go Bookstore API

This is a RESTful API for managing a bookstore, built using Golang, Gorilla Mux, and GORM with MySQL.

## Features
- Add a new book
- Retrieve all books
- Retrieve a book by ID
- Update book details
- Delete a book

## Tech Stack
- **Golang** – Backend development
- **Gorilla Mux** – Routing
- **GORM** – ORM for MySQL
- **MySQL** – Database

## Project Structure
```
/goDatabase
│── cmd
│   └── main.go          # Entry point of the application
│── pkg
│   ├── config
│   │   └── app.go       # Database configuration
│   ├── controllers
│   │   └── book_controller.go # API handlers
│   ├── models
│   │   └── book.go      # Database model
│   ├── routes
│   │   └── bookstore_routes.go # API routes
│   ├── utils
│   │   └── utils.go     # Utility functions
│── .env                 # Environment variables
│── go.mod               # Go module file
│── go.sum               # Dependency lock file
```

## Setup Instructions

### Prerequisites
Ensure you have the following installed:
- Golang (>=1.18)
- MySQL
- Git

### Steps to Run
1. Clone the repository:
   ```sh
   git clone https://github.com/ashX04/goDatabase.git
   cd goDatabase
   ```

2. Create a `.env` file in the root directory and add the following:
   ```ini
   DB_USER=root
   DB_PASSWORD=yourpassword
   DB_HOST=127.0.0.1
   DB_NAME=bookstore
   ```

3. Install dependencies:
   ```sh
   go mod tidy
   ```

4. Run the application:
   ```sh
   go run cmd/main.go
   ```

5. The API will be running on `http://localhost:9010`

## API Endpoints

| Method | Endpoint            | Description          |
|--------|---------------------|----------------------|
| POST   | `/book/`            | Add a new book      |
| GET    | `/book/`            | Get all books       |
| GET    | `/book/{bookId}`    | Get book by ID      |
| PUT    | `/book/{bookId}`    | Update book details |
| DELETE | `/book/{bookId}`    | Delete a book       |

## Example Usage
### Add a Book (POST `/book/`)
```sh
curl -X POST http://localhost:9010/book/ -H "Content-Type: application/json" -d '{"name": "Go Programming", "author": "John Doe", "publication": "TechBooks"}'
```

### Get All Books (GET `/book/`)
```sh
curl -X GET http://localhost:9010/book/
```

