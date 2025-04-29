# SQLite Database Guide (C-based Library Loan Management Program)

## 1. Database File Location

- Store the database file in a separate directory (`database/`) within the project.
  - Example: `database/library.db`

## 2. Table Design

Use the following tables:

- **Books**: Stores book information
  - `book_id` (INTEGER PRIMARY KEY AUTOINCREMENT)
  - `title` (TEXT NOT NULL)
  - `author` (TEXT)
  - `publisher` (TEXT)
  - `publication_year` (INTEGER)
  - `isbn` (TEXT UNIQUE)
  - `genre` (TEXT)

- **Members**: Stores member information
  - `member_id` (INTEGER PRIMARY KEY AUTOINCREMENT)
  - `name` (TEXT NOT NULL)
  - `phone` (TEXT)
  - `address` (TEXT)
  - `registration_date` (TEXT)

- **Loans**: Stores book loan information
  - `loan_id` (INTEGER PRIMARY KEY AUTOINCREMENT)
  - `book_id` (INTEGER, FOREIGN KEY REFERENCES Books(book_id))
  - `member_id` (INTEGER, FOREIGN KEY REFERENCES Members(member_id))
  - `loan_date` (TEXT)
  - `due_date` (TEXT)

- **Returns**: Stores book return information
  - `return_id` (INTEGER PRIMARY KEY AUTOINCREMENT)
  - `loan_id` (INTEGER, FOREIGN KEY REFERENCES Loans(loan_id))
  - `return_date` (TEXT)

## 3. Data Type Selection

- `TEXT`: Stores string data (VARCHAR)
- `INTEGER`: Stores integer data
- Dates are stored as `TEXT` type and handled using SQLite's date-related functions.

## 4. Normalization

- Perform normalization to minimize data redundancy and maintain data consistency.
- Use foreign keys to clarify relationships between tables.

## 5. Indexing

Create indexes on the following fields to improve search performance.

```sql
CREATE INDEX idx_books_title ON Books(title);
CREATE INDEX idx_members_name ON Members(name);
CREATE INDEX idx_loans_book_id ON Loans(book_id);
CREATE INDEX idx_loans_member_id ON Loans(member_id);
```

## 6. Foreign Key Constraints
Loans.book_id references Books(book_id).
Loans.member_id references Members(member_id).
Returns.loan_id references Loans.loan_id.

## 7. Transaction Management
Use transactions for data modification operations such as book loans and returns to maintain data consistency.
```
BEGIN TRANSACTION;
-- SQL statements
COMMIT;
```

## 8. Example of Using the SQLite C API
Below is an example of connecting to the database and executing a query using the SQLite C API.
```
#include <stdio.h>
#include <sqlite3.h>

int main() {
    sqlite3 *db;
    int rc = sqlite3_open("database/library.db", &db);

    if (rc != SQLITE_OK) {
        fprintf(stderr, "Cannot open database: %s\n", sqlite3_errmsg(db));
        sqlite3_close(db);
        return -1;
    }

    const char *sql = "CREATE TABLE IF NOT EXISTS Books ("
                      "book_id INTEGER PRIMARY KEY AUTOINCREMENT,"
                      "title TEXT NOT NULL,"
                      "author TEXT,"
                      "isbn TEXT UNIQUE);";

    char *err_msg = NULL;
    if (sqlite3_exec(db, sql, 0, 0, NULL) != SQLITE_OK) {
        fprintf(stderr, "SQL error: %s\n", sqlite3_errmsg(db));
        sqlite3_close(db);
        return -1;
    }

    sqlite3_close(db);
    return 0;
}
```