---
{
    "title": "DAYNAME",
    "language": "zh-CN"
}
---

## 描述

计算日期表达式对应的日期名字。

## 语法

```sql
DAYNAME(<dt>)
```

## 参数

| 参数 | 说明 |
| -- | -- |
| `<dt>` | 需要被计算的日期表达式 |

## 返回值

返回日期表达式对应的日期名字。

## 举例

```sql
select dayname('2007-02-03 00:00:00');
```

```text
+--------------------------------+
| dayname('2007-02-03 00:00:00') |
+--------------------------------+
| Saturday                       |
+--------------------------------+
```