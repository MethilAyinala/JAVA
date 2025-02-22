# Library Management System

A simple **Library Management System** built in Java. This console-based application allows users to manage books in a library by adding new books, viewing all books, and searching for a specific book by its title.

---

## Features
- **Add a Book**: Users can add a book by providing the title and author.
- **View All Books**: Displays all the books currently in the library.
- **Search for a Book**: Users can search for a book by entering its title.
- **Exit the Program**: Allows the user to exit the application gracefully.

---

## How It Works
The program uses a `Book` class to represent a book with two properties: `title` and `author`. The `LibraryManagementSystem` class contains the main logic for the application, including:
- A list to store books (`ArrayList<Book>`).
- A menu-driven interface for user interaction.
- Methods to add, view, and search for books.

---

## Code Structure

### 1. Book Class
The `Book` class represents a book with two private fields: `title` and `author`. It includes:
- A constructor to initialize the book's title and author.
- Getter methods to access the title and author.
- A `toString()` method to display the book's details in a readable format.

```java
class Book {
    private String title;
    private String author;

    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }

    public String getTitle() {
        return title;
    }

    public String getAuthor() {
        return author;
    }

    @Override
    public String toString() {
        return "Title: " + title + ", Author: " + author;
    }
}
