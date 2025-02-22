import java.util.ArrayList;
import java.util.Scanner;

public class LibraryManagementSystem {
    private static ArrayList<Book> library = new ArrayList<>();
    private static Scanner scanner = new Scanner(System.in);

   public static void main(String[] args) {
        while (true) {
            System.out.println("\n--- Library Management System ---");
            System.out.println("1. Add a Book");
            System.out.println("2. View All Books");
            System.out.println("3. Search for a Book");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");

  int choice = scanner.nextInt();
  scanner.nextLine(); // Consume the newline character

  switch (choice) {
        case 1:
        addBook();
        break;
        case 2:
        viewBooks();
        break;
        case 3:
        searchBook();
        break;
        case 4:
        System.out.println("Exiting the program. Goodbye!");
        System.exit(0);
        break;
        default:
        System.out.println("Invalid choice. Please try again.");
            }
        }
    }

  private static void addBook() {
        System.out.print("Enter the title of the book: ");
        String title = scanner.nextLine();
        System.out.print("Enter the author of the book: ");
        String author = scanner.nextLine();

  Book newBook = new Book(title, author);
        library.add(newBook);
        System.out.println("Book added successfully!");
    }

  private static void viewBooks() {
        if (library.isEmpty()) {
            System.out.println("No books in the library.");
        } else {
            System.out.println("\n--- List of Books ---");
            for (Book book : library) {
                System.out.println(book);
            }
        }
    }

  private static void searchBook() {
        System.out.print("Enter the title of the book to search: ");
        String searchTitle = scanner.nextLine();

   boolean found = false;
        for (Book book : library) {
            if (book.getTitle().equalsIgnoreCase(searchTitle)) {
                System.out.println("Book found: " + book);
                found = true;
                break;
            }
        }

  if (!found) {
            System.out.println("Book not found.");
        }
    }
}
