# Stored procedures

TODO

## Multi-purpose procedures

- Multi-purpose stored procedures
    + More functionality
    + Bad query plan w/ parameter sniffing
- Solutions
    + OPTION RECOMPILE
    + Hybrid - recompile based on input params - using `sp_executesql`
    + Hybrid - using `EXEC`

TODO read

- https://www.sqlskills.com/blogs/kimberly/high-performance-procedures/
- https://www.sqlskills.com/blogs/kimberly/little-bobby-tables-sql-injection-and-execute-as/
