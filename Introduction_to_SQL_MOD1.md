
# SQL

SQL: Structured Query Language. It allows us to communicate with a database. It is the most common language of communication to 
relational database management system (RDBMS), which itself is a software system that deals with relational databases. These 
types of databases basically contain data in simple table formats, showing information for one type of entity. Every row/record represents
an entity, and every column/field represents an attribute for all the rows in that table. Known RDBMS which use SQL are: Oracle, Sybase, Microsoft SQL Server, 
Access, Ingres, etc. These share a basis, but often have extensions to this that are specific to their own system. Here we will 
learn some of these basics. Like: creating, manipulating, and querying. We will learn in PostgreSQL, which is a successor or Ingres. this RDBMS is free and open-source.

## Selecting

Use command `SELECT`  to access the table and the column in that table.

### Selecting Individual Columns

If we have a table called "people", and a column called "name", we can find items in that table and column by:
 `SELECT name FROM people`
 
 In SQL, words like SELECT and FROM are known as keywords. Despite them not being case sensitive, we will use them in capitals here 
 to make it easier to spot them we are using each keyword.
 
Note, SQL queries are also ended with a `;` . This makes it possible for SQL to know when we have reached the end of the query.

### Selecting Multiple Columns

To select more than one column, separate the column names by commas:
`SELECT name, birthdplace FROM people;`

To select all columns, use an asterisk:
`SELECT * FROM people;`

Sometimes, you don't want to see all the rows, in this case you can select how many you want:
`SELECT name FROM people LIMIT 10;`

### Selecting Unique Entries

Selecting unique entries in particular columns is also possible. Using the keyword DISTINCT, eg.:
`SELECT DISTINCT language FROM films;`

This will go through the column language and see what distinct entries there are in all the rows of that column, in the films table.
Thus, it will return with many languages, but none repeated.

### Selecting and Counting

Some times tables are long, and you want to find out how many rows there are for a specific table. For this you can use COUNT, eg.:
`SELECT COUNT(*) FROM people;`
This will count all the rows from table people.

But there are moments, when you find missing values in the table, therefore counting how many rows with data for each column is more
sensible. This can be done with:
`SELECT COUNT(birthplace) FROM people;`

You can mix keywords too, like investigating how many difference places people come from, eg:
`SELECT COUNT(DISTINCT brithplace) FROM people;`


