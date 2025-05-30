---
{
    "title": "JSON_VALID",
    "language": "en"
}
---

<!-- 
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
-->

## Description

The JSON_VALID function returns 0 or 1 to indicate whether the input is a valid JSON. If the input is NULL, it returns NULL.

## Syntax

```sql
JSON_VALID( <str> )

```

Required Parameters
| Parameter | Description |
|------|------|
| `<str>` | The input string in JSON format to be parsed. |

## Alias

- JSONB_VALID

## Examples

1. Valid JSON string

```sql
SELECT json_valid('{"k1":"v31","k2":300}');
+-------------------------------------+
| json_valid('{"k1":"v31","k2":300}') |
+-------------------------------------+
|                                   1 |
+-------------------------------------+

```

2. Invalid JSON string

```sql
SELECT json_valid('invalid json');
+----------------------------+
| json_valid('invalid json') |
+----------------------------+
|                          0 |
+----------------------------+

```

3. NULL 参数

```sql
SELECT json_valid(NULL);
+------------------+
| json_valid(NULL) |
+------------------+
|             NULL |
+------------------+

```
