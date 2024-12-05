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
