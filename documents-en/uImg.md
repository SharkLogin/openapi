### Basic information

> POST /api/v2/plugin/open/uImg

Interface description: Single image upload

### Request parameters

|Parameter Name|Type|Required|Explain|
|:----| :-- | :-- | :--- |
| file | file | Yes | Uploaded file, PostForm request |

Execution successful

```json
{
  "code": 200,
  "data": {
    "crx": {
      "name": "",
      "url": "",
      "tag": ""
    }
  },
  "msg": "Operation successful",
  "requestId": ""
}
```

|Parameter Name|Type|Explain|
|:----| :-- | :-- |
|tag|string|file format|
|name|string|name|
|url|string|File address|

Execution failed

```json
{
  "code": 30008,
  "data": {},
  "msg": "Acquisition failed",
  "requestId": ""
}
```

