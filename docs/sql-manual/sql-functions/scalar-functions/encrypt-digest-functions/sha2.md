---
{
"title": "SHA2",
"language": "en"
}
---

## Description

The information is digested using SHA2.

## Syntax

```sql
SHA2( <str>, <digest_length>)
```

## Parameters

| parameter         | description                |
|-------------------|----------------------------|
| `<str>`           | Content to be encrypted                     |
| `<digest_length>` | Summary length, supports 224, 256, 384, 512. must be constant |

## Return Value

Returns the sha2 value of the input string

## Examples

```sql
select sha2('abc', 224), sha2('abc', 384), sha2(NULL, 512);
```

```text
+----------------------------------------------------------+--------------------------------------------------------------------------------------------------+-----------------+
| sha2('abc', 224)                                         | sha2('abc', 384)                                                                                 | sha2(NULL, 512) |
+----------------------------------------------------------+--------------------------------------------------------------------------------------------------+-----------------+
| 23097d223405d8228642a477bda255b32aadbce4bda0b3f7e36c9da7 | cb00753f45a35e8bb5a03d699ac65007272c32ab0eded1631a8b605a43ff5bed8086072ba1e7cc2358baeca134c825a7 | NULL            |
+----------------------------------------------------------+--------------------------------------------------------------------------------------------------+-----------------+
```

```SQL
select sha2('abc', 225);
```

```text
ERROR 1105 (HY000): errCode = 2, detailMessage = sha2 functions only support digest length of [224, 256, 384, 512]
```

```SQL
select sha2('str', k1) from str;
```

```text
ERROR 1105 (HY000): errCode = 2, detailMessage = the second parameter of sha2 must be a literal but got: k1
```

```SQL
select sha2(k0, k1) from str;
```

```text
ERROR 1105 (HY000): errCode = 2, detailMessage = the second parameter of sha2 must be a literal but got: k1
```
