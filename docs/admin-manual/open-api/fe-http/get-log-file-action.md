---
{
    "title": "Get FE log file",
    "language": "en"
}
---

# Get FE log file

## Request

`HEAD /api/get_log_file`

`GET /api/get_log_file`

## Description

Users can obtain FE log files through the HTTP interface.

The HEAD request is used to obtain the log file list of the specified log type. GET request is used to download the specified log file.
    
## Path parameters

None

## Query parameters

* `type`

    Specify the log type. The following types are supported:
    
    * `fe.audit.log`: Audit log of Frontend.

* `file`

    Specify file name


## Request body

None

## Response

* `HEAD`

    ```
    HTTP/1.1 200 OK
    file_infos: {"fe.audit.log":24759,"fe.audit.log.20190528.1":132934}
    content-type: text/html
    connection: keep-alive
    ```
    
    The returned header lists all current log files of the specified type and the size of each file.
    
* `GET`

    Download the specified log file in text form
    
## Examples

1. Get the log file list of the corresponding type

    ```
    HEAD /api/get_log_file?type=fe.audit.log
    
    Response:
    
    HTTP/1.1 200 OK
    file_infos: {"fe.audit.log":24759,"fe.audit.log.20190528.1":132934}
    content-type: text/html
    connection: keep-alive
    ```
    
    In the returned header, the `file_infos` field displays the file list and the corresponding file size (in bytes) in json format
    
2. Download log file
    
    ```
    GET /api/get_log_file?type=fe.audit.log&file=fe.audit.log.20190528.1
    
    Response:
    
    < HTTP/1.1 200
    < Vary: Origin
    < Vary: Access-Control-Request-Method
    < Vary: Access-Control-Request-Headers
    < Content-Disposition: attachment;fileName=fe.audit.log
    < Content-Type: application/octet-stream;charset=UTF-8
    < Transfer-Encoding: chunked
    
    ... File Content ...
    ```
