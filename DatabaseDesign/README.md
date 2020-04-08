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

* **For reduce data redundancy and improve data integrity**
* **Recommend for 2NF-3NF (ทำแค่ระดับ 2-3 ก็เพียงพอ)**

### 1NF: First normal form
* Primary key (recommend GUID), 
* No repeating group
* Atomic columns (cells have single value) - Column มีข้อมูลเค่าเดียว

### 2NF: Second normal form
* No partial dependencies (values depend on the whole of every Candidate key)

### 3NF: Third normal form
* No transitive dependencies (values depend only on Candidate keys)

### For more detail
https://en.wikipedia.org/wiki/Database_normalization

## Primary Key

### Guid vs INT Which is better as a primary key?

**Prefer: GUID** 

**GUID Pros**

* Unique across every table, every database and every server
* Allows easy merging of records from different databases
* Allows easy distribution of databases across multiple servers
* You can generate IDs anywhere, instead of having to roundtrip to the database
* Most replication scenarios require GUID columns anyway

**GUID Cons**
* It is a whopping 4 times larger than the traditional 4-byte index value
* Cumbersome to debug (where userid='{BAE7DF4-DDF-3RG-5TY3E3RF456AS10}')

### For more detail
https://dba.stackexchange.com/questions/264/guid-vs-int-which-is-better-as-a-primary-key
https://blog.codinghorror.com/primary-keys-ids-versus-guids/

## Database indexing

* Avoid overindexing tables
* Index columns used in foreign keys
* Index columns frequently used in joins
* Use composite indexes and covering indexes to give the query optimizer greater flexibility.

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

### For more detail
https://medium.com/quick-code/10-best-database-design-practices-1f10f3441730
https://dzone.com/articles/20-database-design-best


## Other

**“WITH (NOLOCK)” Hint for select statement**

**What does the SQL Server NOLOCK hint do?**
* The NOLOCK hint allows SQL to read data from tables by ignoring any locks and therefore not being blocked by other processes.
* This can improve query performance, but also introduces the possibility of dirty reads.

