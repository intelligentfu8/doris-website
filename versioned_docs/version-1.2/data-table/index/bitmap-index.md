---
{
    "title": "Bitmap Index",
    "language": "en"
}
---

# Bitmap Index
Users can speed up queries by creating a bitmap index
This document focuses on how to create an index job, as well as some considerations and frequently asked questions when creating an index.

## Glossary
* bitmap index: a fast data structure that speeds up queries

## Basic Principles
Creating and dropping index is essentially a schema change job. For details, please refer to
[Schema Change](../../advanced/alter-table/schema-change.md).

## Syntax
### Create index

Create a bitmap index for siteid on table1

```sql
CREATE INDEX [IF NOT EXISTS] index_name ON table1 (siteid) USING BITMAP COMMENT 'balabala';
```

### View index

Display the lower index of the specified table_name

```sql
SHOW INDEX FROM example_db.table_name;
```

### Delete index

Delete the lower index of the specified table_name

```sql
DROP INDEX [IF EXISTS] index_name ON [db_name.]table_name;
```

## Notice
* Currently only index of bitmap type is supported.
* The bitmap index is only created on a single column.
* Bitmap indexes can be applied to all columns of the `Duplicate` , `Uniq`  data model and key columns of the `Aggregate`  models.
* The data types supported by bitmap indexes are as follows:
    * `TINYINT`
    * `SMALLINT`
    * `INT`
    * `BIGINT`
    * `CHAR`
    * `VARCHAR`
    * `DATE`
    * `DATETIME`
    * `LARGEINT`
    * `DECIMAL`
    * `BOOL`
* The bitmap index takes effect only in segmentV2. The table's storage format will be converted to V2 automatically when creating index.

### More Help

For more detailed syntax and best practices for using bitmap indexes, please refer to the  [CREARE INDEX](../../sql-manual/sql-reference/Data-Definition-Statements/Create/CREATE-INDEX.md) / [SHOW INDEX](../../sql-manual/sql-reference/Show-Statements/SHOW-INDEX.md) / [DROP INDEX](../../sql-manual/sql-reference/Data-Definition-Statements/Drop/DROP-INDEX.md)  command manual. You can also enter HELP CREATE INDEX / HELP SHOW INDEX / HELP DROP INDEX on the MySql client command line.
