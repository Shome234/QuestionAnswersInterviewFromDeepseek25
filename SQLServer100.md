Here’s a comprehensive list of *100 most asked SQL Server interview questions and answers* for experienced developers. These questions cover a wide range of topics, including SQL Server fundamentals, query optimization, indexing, stored procedures, transactions, and advanced features.

---

### *1. SQL Server Fundamentals*
1. *What is SQL Server?*
   - *Answer*: SQL Server is a relational database management system (RDBMS) developed by Microsoft.

2. *What are the editions of SQL Server?*
   - *Answer*: Enterprise, Standard, Web, Developer, and Express.

3. *What is the difference between SQL Server and MySQL?*
   - *Answer*: 
     - *SQL Server*: Developed by Microsoft, supports T-SQL, and is tightly integrated with Windows.
     - *MySQL*: Open-source, supports SQL, and is platform-independent.

4. **What is the purpose of the master database?**
   - *Answer*: It stores system-level information, such as logins, linked servers, and configuration settings.

5. **What is the purpose of the tempdb database?**
   - *Answer*: It stores temporary objects, such as temporary tables and table variables.

6. **What is the purpose of the msdb database?**
   - *Answer*: It stores information related to SQL Server Agent, such as jobs, alerts, and backups.

7. **What is the purpose of the model database?**
   - *Answer*: It serves as a template for creating new databases.

8. **What is the purpose of the resource database?**
   - *Answer*: It stores system objects, such as stored procedures and functions, and is read-only.

9. **What is the difference between SQL Server and Azure SQL Database?**
   - *Answer*: 
     - *SQL Server*: On-premises or self-hosted.
     - *Azure SQL Database*: Cloud-based, fully managed by Microsoft.

10. *What is the purpose of SQL Server Management Studio (SSMS)?*
    - *Answer*: It is a graphical tool for managing and administering SQL Server.

---

### *2. SQL Server Query Optimization*
11. **What is the purpose of the EXPLAIN or EXPLAIN PLAN in SQL Server?**
    - *Answer*: It shows the execution plan of a query, helping to identify performance bottlenecks.

12. **What is the difference between EXPLAIN and SHOWPLAN?**
    - *Answer*: 
      - *EXPLAIN*: Used in MySQL and PostgreSQL.
      - *SHOWPLAN*: Used in SQL Server to display the execution plan.

13. **What is the purpose of the OPTION (RECOMPILE) hint?**
    - *Answer*: It forces SQL Server to recompile the query, which can improve performance for queries with varying parameters.

14. **What is the purpose of the WITH (NOLOCK) hint?**
    - *Answer*: It allows reading uncommitted data, improving performance but risking dirty reads.

15. **What is the difference between NOLOCK and READ UNCOMMITTED?**
    - *Answer*: 
      - *NOLOCK*: Table-level hint.
      - *READ UNCOMMITTED*: Transaction-level isolation level.

16. **What is the purpose of the INDEX hint?**
    - *Answer*: It forces SQL Server to use a specific index for a query.

17. **What is the purpose of the FORCE ORDER hint?**
    - *Answer*: It forces SQL Server to join tables in the order specified in the query.

18. **What is the purpose of the MAXDOP hint?**
    - *Answer*: It limits the degree of parallelism for a query.

19. **What is the purpose of the OPTIMIZE FOR hint?**
    - *Answer*: It instructs SQL Server to optimize a query for specific parameter values.

20. **What is the purpose of the QUERYTRACEON hint?**
    - *Answer*: It enables specific query-level trace flags for debugging or optimization.

---

### *3. SQL Server Indexing*
21. *What is an index in SQL Server?*
    - *Answer*: It is a database object that improves the speed of data retrieval operations.

22. *What is the difference between a **clustered* and *non-clustered* index?**
    - *Answer*: 
      - *Clustered Index*: Determines the physical order of data in a table.
      - *Non-Clustered Index*: Stores a separate structure with pointers to the data.

23. *What is the purpose of a **composite index?*
    - *Answer*: It is an index on multiple columns, used to optimize queries that filter on those columns.

24. *What is the difference between a **unique index* and a *primary key?*
    - *Answer*: 
      - *Unique Index*: Ensures uniqueness but allows null values.
      - *Primary Key*: Ensures uniqueness and does not allow null values.

25. *What is the purpose of a **covering index?*
    - *Answer*: It includes all columns needed by a query, eliminating the need to access the table.

26. *What is the difference between a **covering index* and a *non-covering index?*
    - *Answer*: 
      - *Covering Index*: Includes all columns needed by a query.
      - *Non-Covering Index*: Requires additional lookups to retrieve data.

27. *What is the purpose of a **filtered index?*
    - *Answer*: It is an index on a subset of rows, useful for queries that filter on specific conditions.

28. *What is the difference between a **filtered index* and a *full-table index?*
    - *Answer*: 
      - *Filtered Index*: Indexes only a subset of rows.
      - *Full-Table Index*: Indexes all rows in a table.

29. *What is the purpose of **index fragmentation?*
    - *Answer*: It occurs when index pages are not stored contiguously, reducing performance.

30. *What is the difference between **internal fragmentation* and *external fragmentation?*
    - *Answer*: 
      - *Internal Fragmentation*: Occurs within index pages.
      - *External Fragmentation*: Occurs between index pages.

---

### *4. SQL Server Stored Procedures*
31. *What is a stored procedure?*
    - *Answer*: It is a precompiled collection of SQL statements stored in the database.

32. **What is the purpose of sp_executesql?**
    - *Answer*: It executes a dynamic SQL statement with parameters.

33. **What is the difference between sp_executesql and EXEC?**
    - *Answer*: 
      - *sp_executesql*: Supports parameterized queries.
      - *EXEC*: Executes a SQL string without parameterization.

34. **What is the purpose of OUTPUT parameters in stored procedures?**
    - *Answer*: They allow returning values from a stored procedure to the caller.

35. **What is the difference between OUTPUT and RETURN in stored procedures?**
    - *Answer*: 
      - *OUTPUT*: Returns multiple values.
      - *RETURN*: Returns a single integer value.

36. **What is the purpose of TRY...CATCH in stored procedures?**
    - *Answer*: It handles errors and exceptions in SQL Server.

37. **What is the difference between RAISERROR and THROW?**
    - *Answer*: 
      - *RAISERROR*: Older method for raising errors.
      - *THROW*: Newer method, simpler syntax.

38. **What is the purpose of WITH RECOMPILE in stored procedures?**
    - *Answer*: It forces SQL Server to recompile the stored procedure each time it is executed.

39. **What is the difference between WITH RECOMPILE and OPTION (RECOMPILE)?**
    - *Answer*: 
      - *WITH RECOMPILE*: Recompiles the entire stored procedure.
      - *OPTION (RECOMPILE)*: Recompiles only the specific query.

40. **What is the purpose of SET NOCOUNT ON in stored procedures?**
    - *Answer*: It suppresses the "rows affected" message, improving performance.

---

### *5. SQL Server Transactions*
41. *What is a transaction in SQL Server?*
    - *Answer*: It is a sequence of operations performed as a single logical unit of work.

42. *What are the ACID properties of a transaction?*
    - *Answer*: 
      - *Atomicity*: All operations succeed or fail together.
      - *Consistency*: Data remains consistent before and after the transaction.
      - *Isolation*: Transactions are isolated from each other.
      - *Durability*: Changes are permanent once committed.

43. **What is the purpose of BEGIN TRANSACTION?**
    - *Answer*: It starts a new transaction.

44. **What is the difference between COMMIT and ROLLBACK?**
    - *Answer*: 
      - *COMMIT*: Saves changes made during the transaction.
      - *ROLLBACK*: Undoes changes made during the transaction.

45. **What is the purpose of SAVE TRANSACTION?**
    - *Answer*: It creates a savepoint within a transaction, allowing partial rollback.

46. **What is the difference between SAVE TRANSACTION and ROLLBACK TO?**
    - *Answer*: 
      - *SAVE TRANSACTION*: Creates a savepoint.
      - **ROLLBACK TO`: Rolls back to a specific savepoint.

47. **What is the purpose of SET TRANSACTION ISOLATION LEVEL?**
    - *Answer*: It sets the isolation level for a transaction, controlling how transactions interact with each other.

48. **What is the difference between READ UNCOMMITTED and READ COMMITTED?**
    - *Answer*: 
      - *READ UNCOMMITTED*: Allows dirty reads.
      - *READ COMMITTED*: Prevents dirty reads.

49. **What is the purpose of WITH (NOLOCK)?**
    - *Answer*: It allows reading uncommitted data, improving performance but risking dirty reads.

50. **What is the difference between WITH (NOLOCK) and READ UNCOMMITTED?**
    - *Answer*: 
      - *WITH (NOLOCK)*: Table-level hint.
      - *READ UNCOMMITTED*: Transaction-level isolation level.

---

### *6. SQL Server Advanced Features*
51. *What is the purpose of **Common Table Expressions (CTEs)?*
    - *Answer*: They allow creating temporary result sets that can be referenced within a query.

52. *What is the difference between a **CTE* and a *subquery?*
    - *Answer*: 
      - *CTE*: Can be referenced multiple times in a query.
      - *Subquery*: Can only be referenced once.

53. *What is the purpose of **Window Functions?*
    - *Answer*: They perform calculations across a set of rows related to the current row.

54. **What is the difference between ROW_NUMBER() and RANK()?**
    - *Answer*: 
      - *ROW_NUMBER()*: Assigns a unique number to each row.
      - *RANK()*: Assigns the same rank to rows with the same value, leaving gaps.

55. *What is the purpose of **PIVOT* and *UNPIVOT?*
    - *Answer*: 
      - *PIVOT*: Converts rows into columns.
      - *UNPIVOT*: Converts columns into rows.

56. *What is the purpose of **Dynamic SQL?*
    - *Answer*: It allows constructing and executing SQL statements dynamically at runtime.

57. *What is the difference between **Dynamic SQL* and *Static SQL?*
    - *Answer*: 
      - *Dynamic SQL*: Constructed and executed at runtime.
      - *Static SQL*: Predefined and compiled.

58. *What is the purpose of **Full-Text Search?*
    - *Answer*: It allows searching for words or phrases within text data.

59. *What is the difference between **Full-Text Search* and *LIKE?*
    - *Answer*: 
      - *Full-Text Search*: Supports advanced search features like stemming and ranking.
      - *LIKE*: Supports simple pattern matching.

60. *What is the purpose of **SQL Server Agent?*
    - *Answer*: It automates tasks such as backups, job scheduling, and alerts.

---

### *7. SQL Server Security*
61. *What is the purpose of **SQL Server Authentication?*
    - *Answer*: It allows users to log in to SQL Server using a username and password.

62. *What is the difference between **SQL Server Authentication* and *Windows Authentication?*
    - *Answer*: 
      - *SQL Server Authentication*: Uses a username and password.
      - *Windows Authentication*: Uses Windows user accounts.

63. *What is the purpose of **roles* in SQL Server?**
    - *Answer*: They group users and permissions for easier management.

64. *What is the difference between **server roles* and *database roles?*
    - *Answer*: 
      - *Server Roles*: Apply to the entire SQL Server instance.
      - *Database Roles*: Apply to a specific database.

65. *What is the purpose of **schemas* in SQL Server?**
    - *Answer*: They group database objects (e.g., tables, views) for easier management.

66. *What is the difference between **schemas* and *databases?*
    - *Answer*: 
      - *Schemas*: Group objects within a database.
      - *Databases*: Contain schemas and other database objects.

67. *What is the purpose of **encryption* in SQL Server?**
    - *Answer*: It protects sensitive data by converting it into an unreadable format.

68. *What is the difference between **Transparent Data Encryption (TDE)* and *Column-Level Encryption?*
    - *Answer*: 
      - *TDE*: Encrypts the entire database.
      - *Column-Level Encryption*: Encrypts specific columns.

69. *What is the purpose of **auditing* in SQL Server?**
    - *Answer*: It tracks and logs database activities for security and compliance.

70. *What is the difference between **SQL Server Audit* and *SQL Trace?*
    - *Answer*: 
      - *SQL Server Audit*: Tracks specific events for compliance.
      - *SQL Trace*: Captures detailed performance and diagnostic data.

---

### *8. SQL Server Performance Tuning*
71. *What is the purpose of **query optimization?*
    - *Answer*: It improves the performance of SQL queries by reducing execution time and resource usage.

72. *What is the difference between **query optimization* and *index optimization?*
    - *Answer*: 
      - *Query Optimization*: Focuses on improving query execution.
      - *Index Optimization*: Focuses on improving index usage.

73. *What is the purpose of **execution plans?*
    - *Answer*: They show how SQL Server executes a query, helping to identify performance bottlenecks.

74. *What is the difference between **estimated* and *actual* execution plans?**
    - *Answer*: 
      - *Estimated Execution Plan*: Shows the plan before execution.
      - *Actual Execution Plan*: Shows the plan after execution.

75. *What is the purpose of **statistics* in SQL Server?**
    - *Answer*: They provide information about data distribution, helping the query optimizer make better decisions.

76. *What is the difference between **auto-update statistics* and *manual statistics?*
    - *Answer*: 
      - *Auto-Update Statistics*: Automatically updated by SQL Server.
      - *Manual Statistics*: Updated manually by the user.

77. *What is the purpose of **query hints?*
    - *Answer*: They provide instructions to the query optimizer to influence query execution.

78. *What is the difference between **query hints* and *index hints?*
    - *Answer*: 
      - *Query Hints*: Influence the entire query.
      - *Index Hints*: Influence the use of specific indexes.

79. *What is the purpose of **database partitioning?*
    - *Answer*: It splits large tables into smaller, more manageable pieces for better performance.

80. *What is the difference between **horizontal* and *vertical partitioning?*
    - *Answer*: 
      - *Horizontal Partitioning*: Splits rows into separate tables.
      - *Vertical Partitioning*: Splits columns into separate tables.

---

### *9. SQL Server Backup and Recovery*
81. *What is the purpose of **backups* in SQL Server?**
    - *Answer*: They provide a way to restore data in case of failure or corruption.

82. *What is the difference between **full, **differential, and **transaction log* backups?**
    - *Answer*: 
      - *Full Backup*: Backs up the entire database.
      - *Differential Backup*: Backs up changes since the last full backup.
      - *Transaction Log Backup*: Backs up the transaction log for point-in-time recovery.

83. *What is the purpose of **restore* in SQL Server?**
    - *Answer*: It recovers a database from a backup.

84. *What is the difference between **restore* and *recovery?*
    - *Answer*: 
      - *Restore*: Copies data from a backup.
      - *Recovery*: Brings the database to a consistent state.

85. *What is the purpose of **point-in-time recovery?*
    - *Answer*: It allows restoring a database to a specific point in time using transaction log backups.

86. *What is the difference between **point-in-time recovery* and *full recovery?*
    - *Answer*: 
      - *Point-in-Time Recovery*: Restores to a specific time.
      - *Full Recovery*: Restores the entire database.

87. *What is the purpose of **database snapshots?*
    - *Answer*: They provide a read-only view of a database at a specific point in time.

88. *What is the difference between **snapshots* and *backups?*
    - *Answer*: 
      - *Snapshots*: Provide a point-in-time view of the database.
      - *Backups*: Provide a copy of the database for recovery.

89. *What is the purpose of **mirroring* in SQL Server?**
    - *Answer*: It creates a real-time copy of a database for high availability.

90. *What is the difference between **mirroring* and *replication?*
    - *Answer*: 
      - *Mirroring*: Creates a real-time copy for high availability.
      - *Replication*: Creates copies for scalability or disaster recovery.

---

### *10. SQL Server Advanced Concepts*
91. *What is the purpose of **Always On Availability Groups?*
    - *Answer*: They provide high availability and disaster recovery for databases.

92. *What is the difference between **Always On Availability Groups* and *Database Mirroring?*
    - *Answer*: 
      - *Always On Availability Groups*: Supports multiple databases and read-only replicas.
      - *Database Mirroring*: Supports only one database.

93. *What is the purpose of **SQL Server Integration Services (SSIS)?*
    - *Answer*: It is a tool for data integration and ETL (Extract, Transform, Load) processes.

94. *What is the difference between **SSIS* and *SQL Server Reporting Services (SSRS)?*
    - *Answer*: 
      - *SSIS*: Used for data integration.
      - *SSRS*: Used for generating reports.

95. *What is the purpose of **SQL Server Analysis Services (SSAS)?*
    - *Answer*: It is a tool for data analysis and business intelligence.

96. *What is the difference between **SSAS* and *SSRS?*
    - *Answer*: 
      - *SSAS*: Used for data analysis.
      - *SSRS*: Used for generating reports.

97. *What is the purpose of **PolyBase* in SQL Server?**
    - *Answer*: It allows querying external data sources (e.g., Hadoop, Azure Blob Storage) using T-SQL.

98. *What is the difference between **PolyBase* and *Linked Servers?*
    - *Answer*: 
      - *PolyBase*: Optimized for big data sources.
      - *Linked Servers*: Used for connecting to other SQL Server instances or databases.

99. *What is the purpose of **In-Memory OLTP* in SQL Server?**
    - *Answer*: It improves performance for transactional workloads by storing data in memory.

100. *What is the difference between **In-Memory OLTP* and *Disk-Based Tables?*
     - *Answer*: 
       - *In-Memory OLTP*: Stores data in memory for faster access.
       - *Disk-Based Tables*: Stores data on disk.

---

These questions and answers should help you prepare for SQL Server interviews at an experienced level. Let me know if you need further clarification!
