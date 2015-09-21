---
layout: post
title: MS SQL - Random Tips
tags: [Documentation]
---

### Stored Procedure
- You cannot use FUNCTIONS like GETDATE(), in assigning default value to the Stored Procedure input parameters. 

```sql
Create Procedure spName
(
	@InputDate datetime = NULL
)
AS
    if @InputDate is null
        set @InputDate = GETDATE()
```


### Database management

- Truncating a huge sized table will not reduce the database size. After TRUNCATE, you need to *shrink* the database.  
**Using SSMS:** Right Click on Database Name-->Tasks-->Shrink-->Database. 
To reduce log file size, Right Click on Database Name-->Tasks-->Shrink-->Files. 

**Using SQL Query:** Run following sql query.
```sql
dbcc shrinkdatabase (DatabaseName,truncateonly)
dbcc shrinkfile (DatabaseName_log, 10, truncateonly)
```