---
{
"title": "SM3",
"language": "zh-CN"
}
---

## 描述

计算 SM3 256-bit

## 语法

```sql
SM3( <str> )
```

## 参数

| 参数      | 说明         |
|---------|------------|
| `<str>` | 需要被计算 sm3 的值 |

## 返回值
返回输入字符串的 sm3 值

## 示例

```sql
select sm3("abcd");
```

```text
+------------------------------------------------------------------+
| sm3('abcd')                                                      |
+------------------------------------------------------------------+
| 82ec580fe6d36ae4f81cae3c73f4a5b3b5a09c943172dc9053c69fd8e18dca1e |
+------------------------------------------------------------------+
```
