# Database Design Guide

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

