---
layout: post
title: How to Export SQL query output to CSV file with and Without header? 
tags: [jekyll, documentation]
---

bcp or sqlcmd commands can be used to achieve this.

####SQLCMD - With header:


All names in CAP need to be defined according to your environment /db.

```bash
sqlcmd -S SERVERNAME -d DATABASE_NAME -E -o "c:\EXPORTED_CSV_FILE.csv" -Q "select * from TABLENAME" -W -w 999 -s","
```

* -W   remove trailing spaces from each individual field 
* -s","   sets the column seperator to the comma (,)
* -w 999   sets the row width to 999 chars


####SQLCMD - Without header:
```sql
sqlcmd -S SERVERNAME -d DATABASE_NAME -E -o "c:\EXPORTED_CSV_FILE.csv" -Q "select * from TABLENAME" -W -w 999 -s"," -h-1
```

* -h-1 removes column name headers from the result 


####bcp Command:
```sql
bcp "select * from DATABASE.SCHEMA.TABLE" queryout  "c:\EXPORTED_CSV_FILE.csv"  -c -t"," -r"\n" -S SERVERNAME -T
```
