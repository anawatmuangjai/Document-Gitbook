---
description: Basic database design!
---

# Database Design Guidelines

## Naming Conventions

* Object names are easily understood
* Table names are not pluralized ("User" table not "Users")
* Abbreviations are few, but allowed (i.e. Qty, Amt, etc.)
* PascalCase used exclusively with the exception of certain column names (i.e. rowguid)
* No underscores
* Certain keywords are allowed (i.e. Name)
* Stored procedures are prefaced with "usp"
* Functions are prefaced with "ufn"

### For more detail 
https://stackoverflow.com/questions/3593582/database-naming-conventions-by-microsoft

## Database Normalization

* Primary key
* No repeating group
* Atomic columns (cells have single value)
* No partial dependencies

### For more detail
https://en.wikipedia.org/wiki/Database_normalization

## Tips & Trick

* Use a naming convention
* Use short, meaningful names
* Use the right number of tables
* Avoid repeating data
* Avoid redundant data
* Avoid nulls
* Avoid secret codes
* Use constraints wisely
* Do a clear separation between data fields
* Use boolean and short encoding characters
* Use small numbers when possible
* Use application caching
* Test queries with explain plan
* Too many indexes may slow down the database
* Close transactions as soon as possible

## Other

**“WITH (NOLOCK)” Hint for select statement**

**What does the SQL Server NOLOCK hint do?**
* The NOLOCK hint allows SQL to read data from tables by ignoring any locks and therefore not being blocked by other processes.
* This can improve query performance, but also introduces the possibility of dirty reads.

