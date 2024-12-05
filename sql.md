# SQL

### SQL Query Execution Order  

Understanding the order in which SQL statements are executed is critical for crafting accurate and efficient queries. Here’s the logical sequence in which SQL clauses are processed:  

1. **FROM** - Specifies the source tables for the query.  
2. **JOIN** - Combines data from multiple tables based on a condition.  
3. **WHERE** - Filters rows based on conditions before grouping.  
4. **GROUP BY** - Groups data for aggregation.  
5. **HAVING** - Filters groups based on aggregated data.  
6. **SELECT** - Chooses the columns or expressions to return in the result set.  
7. **OVER** - Applies window functions over partitions of data.  
8. **QUALIFY** - Filters rows based on window function results (used in some SQL dialects like Snowflake).  
9. **ORDER BY** - Sorts the result set by specified columns or expressions.  
10. **LIMIT** - Restricts the number of rows returned in the final output.  

### SQL Command Categories Overview

In SQL, commands are categorized into different groups based on their functionality. Each category serves a unique purpose, ranging from defining database structures to manipulating data and controlling access. Here’s a summary of the four main categories of SQL commands:

| **Category**   | **Purpose**                                   | **Key Commands**                | **Impact**                                                                                  |  
|----------------|-----------------------------------------------|----------------------------------|--------------------------------------------------------------------------------------------|  
| **DDL**        | Defines and manages database structure        | `CREATE`, `ALTER`, `DROP`, `TRUNCATE` | Changes the structure or schema of database objects like tables, views, and indexes.         |  
| **DML**        | Manipulates data in tables                    | `INSERT`, `UPDATE`, `DELETE`, `MERGE` | Modifies the actual data stored in tables, adding, updating, or deleting rows.               |  
| **DCL**        | Controls access to data and objects           | `GRANT`, `REVOKE`               | Manages user permissions and controls access to database objects for security purposes.       |  
| **TCL**        | Manages transactions for data consistency     | `COMMIT`, `ROLLBACK`, `SAVEPOINT` | Ensures data integrity by handling transactions and their effects on the database state.      |  

Let me know if there’s anything else you’d like to adjust!
