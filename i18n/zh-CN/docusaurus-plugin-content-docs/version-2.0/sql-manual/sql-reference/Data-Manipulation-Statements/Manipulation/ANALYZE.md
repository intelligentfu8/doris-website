---
{
    "title": "ANALYZE",
    "language": "zh-CN"
}
---

## ANALYZE

### Name

ANALYZE

## 描述

该语句用于收集各列的统计信息。

```sql
ANALYZE < TABLE | DATABASE table_name | db_name > 
    [ (column_name [, ...]) ]
    [ [ WITH SYNC ] [ WITH SAMPLE PERCENT | ROWS ] ];
```

- table_name: 指定的目标表。可以是  `db_name.table_name`  形式。
- column_name: 指定的目标列。必须是  `table_name`  中存在的列，多个列名称用逗号分隔。
- sync：同步收集统计信息。收集完后返回。若不指定则异步执行并返回 JOB ID。
- sample percent | rows：抽样收集统计信息。可以指定抽样比例或者抽样行数。

## 举例

对一张表按照 10% 的比例采样收集统计数据：

```sql
ANALYZE TABLE lineitem WITH SAMPLE PERCENT 10;
```

对一张表按采样 10 万行收集统计数据

```sql
ANALYZE TABLE lineitem WITH SAMPLE ROWS 100000;
```

### Keywords

ANALYZE
