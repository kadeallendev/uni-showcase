# P2: Library Management System Business Case

For this assignment we assumed the role of a database engineer at a library. We had to create a Java program that would use JDBC to connect to a database to manage books, customers, authors, and loans. The main requirement of the program was for it to be concurrently safe. We had to utilise database transactions to achieve this.

The system was able to:
- Lookup books
- Display catalogue
- Display books out on loan
- Lookup authors
- Display all authors
- Lookup customers
- Display all customers
- Borrow books
- Return books

As an example of the concurrent features: if a book was in the process of being borrowed, any actions that would modify the book or loan record would wait until the borrow action was completed before being performed.
