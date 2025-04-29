# C-based Library Loan Management Program Coding Style Guide

1. **Naming Conventions**:

    *   **Function Names**: Start with a verb and use snake_case in lowercase (e.g., `add_book`, `search_member`, `process_loan`).
    *   **Variable Names**: Use snake_case in lowercase (e.g., `book_id`, `member_name`, `loan_date`).
    *   **Constant Names**: Use all uppercase letters with underscores between words (e.g., `MAX_BOOKS`, `DEFAULT_LOAN_PERIOD`).
    *   **Struct Names**: Use CamelCase starting with an uppercase letter (e.g., `Book`, `Member`, `Loan`).
    *   **File Names**: Use snake_case in lowercase with `.h` and `.c` extensions (e.g., `database.h`, `library.c`).

2. **Code Structure**:

    *   **Header Files**:
        - Struct definitions, constants, and function prototypes are written in header files (`.h`).
        - Example: `book.h`, `member.h`, `loan.h`.
    *   **Source Files**:
        - Function implementations are written in source files (`.c`).
        - Example: `book.c`, `member.c`, `loan.c`.
    *   **Modularization**:
        - Separate each major feature (book management, member management, loan/return management) into its own module.
    *   **Main File**:
        - Define the program entry point in `main.c` and call each module from there.

3. **Comments**:

    *   **Function Comments**:
        - Describe the role of the function, its parameters, and return values.
        - Example:
        ```c
        /**
         * @brief Add a new book to the library database.
         * 
         * @param title The title of the book.
         * @param author The author of the book.
         * @param isbn The ISBN of the book.
         * @return int Returns 0 on success, -1 on failure.
         */
        int add_book(const char *title, const char *author, const char *isbn);
        ```
    *   **Code Block Comments**:
        - Explain complex logic or the reason for important decisions.

4. **Error Handling**:

    *   Functions return `0` on success, `-1` or an appropriate error code on failure.
    *   On database operation failure, print an error message and perform appropriate recovery actions.

5. **Memory Management**:

    *   Use `malloc` and `free` for dynamic memory allocation, and free all allocated memory to prevent memory leaks.
    *   Always close database connections and result sets after use.

6. **SQLite Integration**:

    *   Use the SQLite C API for database operations.
    *   Write SQL queries as strings and use parameter binding to prevent SQL injection.
    *   Open the database connection at program start and close it at termination.

7. **Others**:

    *   Use the `const` keyword to protect data that should not be changed.
    *   Use `#define` to define constants.
    *   Use a code formatter (e.g., `clang-format`) to maintain consistent code style.
  
# Example Code Style

 **Struct Definition**:
```c
// filepath: include/book.h
#ifndef BOOK_H
#define BOOK_H

typedef struct {
    int id;
    char title[100];
    char author[50];
    char isbn[20];
    char genre[30];
    char publisher[50];
    int publication_year;
    int quantity;
    int available;
} Book;

#endif // BOOK_H
```
