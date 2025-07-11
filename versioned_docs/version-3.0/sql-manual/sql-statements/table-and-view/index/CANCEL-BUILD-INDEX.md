---
{
    "title": "CANCEL BUILD INDEX",
    "language": "en"
}
---

## Description

Cancel background tasks for index building.

## Syntax


```sql
CANCEL BUILD INDEX ON <table_name> [ job_list ]
```

其中：

```sql
job_list
  : (<job_id1>[ , job_id2 ][ ... ])
```
## Required Parameters

**<table_name>**

> Specifies the identifier (i.e., name) of the table, which must be unique within its database (Database).
>
> The identifier must start with a letter character (or any language character if unicode name support is enabled) and cannot contain spaces or special characters unless the entire identifier string is enclosed in backticks (e.g., `My Object`).
>
> Identifiers cannot use reserved keywords.
>
> For more details, see Identifier Requirements and Reserved Keywords.

## Optional Parameters

**<job_list>**

> Specifies a list of identifiers for index building tasks, separated by commas and enclosed in parentheses.
>
> Identifiers must be numbers and can be viewed via SHOW BUILD INDEX.

## Access Control Requirements

The user executing this SQL command must have at least the following privileges:

| Privilege  | Object | Notes                                                        |
| :--------- | :----- | :----------------------------------------------------------- |
| ALTER_PRIV | Table  | CANCEL BUILD INDEX is considered an ALTER operation on the table |

## Usage Notes

- Currently only effective for inverted indexes, not for other indexes such as bloomfilter index.
- Currently only effective for the integrated storage and computing mode, not for the separated storage and computing mode.
- The progress and index building tasks of BUILD INDEX can be viewed via SHOW BUILD INDEX.

## Examples

- Cancel all index building tasks on table table1

  ```sql
  CANCEL BUILD INDEX ON TABLE table1
  ```

- Cancel index building tasks jobid1 and jobid2 on table table1

  ```sql
  CANCEL BUILD INDEX ON TABLE table1(jobid1, jobid2)
  ```