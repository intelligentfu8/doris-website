---
{
    "title": "BIN",
    "language": "zh-CN"
}
---

## bin

## 描述
## 语法

`STRING bin(BIGINT x)`
将十进制数`x`转换为二进制数.

## 举例

```
mysql> select bin(0);
+--------+
| bin(0) |
+--------+
| 0      |
+--------+
mysql> select bin(10);
+---------+
| bin(10) |
+---------+
| 1010    |
+---------+
mysql> select bin(-3);
+------------------------------------------------------------------+
| bin(-3)                                                          |
+------------------------------------------------------------------+
| 1111111111111111111111111111111111111111111111111111111111111101 |
+------------------------------------------------------------------+
```

### keywords
	BIN
