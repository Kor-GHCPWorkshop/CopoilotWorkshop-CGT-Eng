* **Function names**: Start with a verb and use snake_case in lowercase (e.g., `add_book`, `search_member`, `process_loan`).
* **Variable names**: Use snake_case in lowercase (e.g., `book_id`, `member_name`, `loan_date`).
* **Constant names**: Use all uppercase letters with underscores between words (e.g., `MAX_BOOKS`, `DEFAULT_LOAN_PERIOD`).
* **Struct names**: Use CamelCase starting with an uppercase letter (e.g., `Book`, `Member`, `Loan`).
* **File names**: Use snake_case in lowercase with `.h` and `.c` extensions (e.g., `database.h`, `library.c`).

* **Header files**:
    - Write struct definitions, constants, and function prototypes in header files (`.h`).
    - Example: `book.h`, `member.h`, `loan.h`.
* **Source files**:
    - Write function implementations in source files (`.c`).
    - Example: `book.c`, `member.c`, `loan.c`.
* **Modularization**:
    - Separate each major feature (book management, member management, loan/return management) into its own module.
* **Main file**:
    - Define the program entry point in `main.c` and call each module from there.