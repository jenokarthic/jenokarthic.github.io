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