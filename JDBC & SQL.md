# SQL
## Concepts
- RDBMS
- Sublanguages: DDL, DML, DQL
- Set Operators: Union, Intersect, Except
- Subqueries
- Normalization: 1st vs 2nd vs 3rd Normal Forms
- Multiplicity: Foreign keys
- Joins: Inner, Outer, Cross
- Functions: Aggregate vs Scalar

## Syntax
- [DDL](https://www.postgresql.org/docs/12/ddl.html): 
  - [CREATE TABLE](https://www.postgresql.org/docs/12/sql-createtable.html)
  - [ALTER TABLE](https://www.postgresql.org/docs/12/sql-altertable.html)
  - [DROP TABLE](https://www.postgresql.org/docs/12/sql-droptable.html)
- [DML](https://www.postgresql.org/docs/12/dml.html): 
  - [INSERT](https://www.postgresql.org/docs/12/sql-insert.html)
  - [UPDATE](https://www.postgresql.org/docs/12/sql-update.html)
  - [DELETE](https://www.postgresql.org/docs/12/sql-delete.html)
- [DQL](https://www.postgresql.org/docs/12/queries.html):
  - [SELECT](https://www.postgresql.org/docs/12/sql-select.html)
  - Combining Queries: [UNION/INTERSECT/EXCEPT](https://www.postgresql.org/docs/12/queries-union.html)
  - [Scalar Subqueries](https://www.postgresql.org/docs/12/sql-expressions.html#SQL-SYNTAX-SCALAR-SUBQUERIES)
  - [Subquery Expressions](https://www.postgresql.org/docs/12/functions-subquery.html)
  - [Joined Tables](https://www.postgresql.org/docs/12/queries-table-expressions.html#QUERIES-JOIN)
- [Functions](https://www.postgresql.org/docs/12/functions.html):
  - [Aggregate Functions](https://www.postgresql.org/docs/12/functions-aggregate.html)
  - Scalar Functions:
    - [Date/Time](https://www.postgresql.org/docs/12/functions-datetime.html)
    - [Math](https://www.postgresql.org/docs/12/functions-math.html)
    - [Strings](https://www.postgresql.org/docs/12/functions-string.html)

# JDBC
Java Database Connectivity (JDBC) is an API for connecting to a RDBMS such as Oracle, PostgreSQL, or MySQL. As a collection of classes and interfaces it requires a driver from the database vendor on the classpath. Once added, a `java.sql.DriverManager` will register the driver and act as a factory for a `java.sql.Connection`, used to create and send SQL queries with `java.sql.Statement`, `java.sql.PreparedStatement`, or `java.sql.CallableStatement` objects, and retrieve result sets in `java.sql.ResultSet` objects.

You can load a JDBC driver using `Class.forName()` or `DriverManager.registerDriver()`, or let DriverManager automatically detect the driver on the classpath.

```java
// Loading the driver may not be necessary, but it's good to specify
try {
    Class.forName("org.postgresql.Driver");
} catch (java.lang.ClassNotFoundException e) {
    System.out.println(e.getMessage());
}

// Pay attention to the url pattern
String url = "jdbc:postgresql://host:port/database";
String username = "databaseuser"
String password = "password"

try (
    // Be sure to close all connections after use
    Connection connection = DriverManager.getConnection(url, username, password);
    Statement statement = connection.createStatement();
){
    // executeUpdate() returns the number of rows affected for DML
    int rowCount = statement.executeUpdate("insert into pizza values (1, 'cheese')");

    // executeQuery() returns a ResultSet object for queries
    ResultSet pizzas = statement.executeQuery("select * from pizza");

    // Loop through ResultSet for each row returned
    while(pizzas.next()) {
        System.out.println(pizzas.getInt("id"));
        System.out.println(pizzas.getString("flavor"));
    }

} catch (SQLException ex) {
    
} 
```

## Statement
A Statement object sends queries and updates, as well as receive errors or ResultSets.

**Statement** is prone to SQL Injection attacks, especially if you use a raw string to write the query.

**PreparedStatement** is a precompiled SQL statement. It is best used for writing several similar queries in a loop, but will also as a side effect protect against SQL Injections
```java
PreparedStatement ps = myConnection.prepareStatement("UPDATE ANIMALS SET name=? WHERE id=?");
ps.setString(1, "Hippo");
ps.setInt(2, 7);
ps.executeQuery();
```
**CallableStatement** execute stored procedures and can return 1 or many ResultSets.
```java
CallableStatement cs = myConnection.prepareCall("{CALL BIRTHDAY_SP(?, ?)}");
cs.setInt(1, aid);
cs.setInt(2, yta);
cs.execute();
```

## Transaction Management
The connection objecct will automatically commit every statement to the database, which may not be ideal for batch insertions. To open a transaction, call `connection.setAutocommit(false)` and end the transaction afterwards with `connection.commit()`, then set `connection.setAutocommit(true)` if needed. Use the `rollback()` method if exceptions are thrown during the transaction.

## Resources
### Articles
- [A beginner’s guide to SQL injection and how you should prevent it](https://vladmihalcea.com/a-beginners-guide-to-sql-injection-and-how-you-should-prevent-it/)
- [The anatomy of Connection Pooling](https://vladmihalcea.com/the-anatomy-of-connection-pooling/)

### Documentation
- [Java JDBC API](https://docs.oracle.com/javase/8/docs/technotes/guides/jdbc/)
- [java.sql (JavaSE 8)](https://docs.oracle.com/javase/8/docs/api/java/sql/package-summary.html)

### Tutorials
- [Oracle Java Tutorials - JDBC Introduction](https://docs.oracle.com/javase/tutorial/jdbc/overview/index.html)
- [Oracle Java Tutorials - JDBC Basics](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html)
- [JDBC Diver Connection URL strings](https://vladmihalcea.com/jdbc-driver-connection-url-strings/)
- [JDBC Driver Maven dependency list](https://vladmihalcea.com/jdbc-driver-maven-dependency/)

## Concepts
- [Java JDBC API](https://docs.oracle.com/javase/8/docs/technotes/guides/jdbc/)

## Standard Library
- [java.sql](https://docs.oracle.com/javase/8/docs/api/java/sql/package-summary.html)
  - [DriverManager](https://docs.oracle.com/javase/8/docs/api/java/sql/DriverManager.html)
  - [Connection](https://docs.oracle.com/javase/8/docs/api/java/sql/Connection.html)
  - [Statement](https://docs.oracle.com/javase/8/docs/api/java/sql/Statement.html)
    - [PreparedStatement](https://docs.oracle.com/javase/8/docs/api/java/sql/PreparedStatement.html)
    - [CallableStatement](https://docs.oracle.com/javase/8/docs/api/java/sql/CallableStatement.html)
  - [ResultSet](https://docs.oracle.com/javase/8/docs/api/java/sql/ResultSet.html)
  - [SQLException](https://docs.oracle.com/javase/8/docs/api/java/sql/SQLException.html)

# Questions
## SQL
- What is SQL?
- What are its sublanguages?
- What is multiplicity?
- What is cardinality?
- What is a candidate key?
- What is referential integrity?
- What are the different constraints of a column?
- what are the differences between GROUP BY and ORDER BY?
- What is the difference between IN and EXISTS?
- What are subqueries?
- What is the differenece between an aggregate function and a scalar function?
- What are the different joins in SQL?
- What are the different set operations in SQL?
- What is the difference between joins and set operations?
- What is normalization?
- What are the requirements for the first three normal forms?

## JDBC
- What is JDBC?
- What dependencies are required to connect to an RDBMS?
- What are the main interfaces of JDBC?
- In what order are they used?
- What are the different types of statements?
- What is SQL Injection?
- What is a DAO?
- Describe client-server communication: how does it apply to PostgreSQL?
- What does a connection URL for PostgreSQL look like?
- How do you connect to a PostgreSQL server with a client? With Java?
- Why is connection pooling important?
