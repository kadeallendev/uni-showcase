# P1: Bank Robbery Business Case

For this assignment we assumed the role of a database engineer working at a city's police department. The police department is investigating a group of bank robbers, and we were tasked with creating a relational database (Postgres) to organise the robbery information, as well as creating queries to evaluate it.

The tasks involved:
- Defining the schema of the database using PostgreSQL
- Populating the database using tab-separated data files
- Check that the database enforces the required constraints by attempting to run invalid queries
- Creating SQL queries to evaluate the robbery information

# Example queries

- What banks were not robbed in a year in which there were plans for that bank to be robbed:
    ```sql
    SELECT DISTINCT BankName, City
    FROM Plans
    EXCEPT
    SELECT DISTINCT b.BankName, b.City
    FROM (
        SELECT BankName, City, EXTRACT(YEAR FROM PlannedDate) AS PlannedYear
        FROM Plans
    ) b
    LEFT JOIN (
        SELECT BankName, City, EXTRACT(YEAR FROM PlannedDate RobberyDate) AS RobberyYear
        FROM Robberies
    ) r
    ON b.BankName = r.BankName
    AND b.City = r.City
    AND b.PlannedYear = r.RobberyYear
    WHERE r.RobberyYear IS NOT NULL;
    ```
- What robbers have never robbed a bank where they have an account:
    ```sql
    SELECT RobberId, Nickname
    FROM Robbers
    EXCEPT
    SELECT DISTINCT accounts.RobberId, accounts.Nickname
    FROM (
        SELECT r.RobberId, r.Nickname, h.BankName, h.City
        FROM Robbers r
        LEFT JOIN HasAccounts h ON r.RobberId = h.RobberId
    ) accounts
    INNER JOIN Accomplices robberies
        ON accounts.RobberId = robberies.RobberId
        AND accounts.BankName = robberies.BankName
        AND accounts.City = robberies.City
    ORDER BY RobberId;
    ```
