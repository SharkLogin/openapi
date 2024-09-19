### Basic information

> POST /api/v2/plugin/open/uFileCrx

Interface description: Upload plugin - Attachment

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
      "tag": "",
      "uuid": ""
    }
  },
  "msg": "Operation successful",
  "requestId": ""
}
```

|Parameter Name|Type|Explain|
|:----| :-- | :-- |
|tag|string|file format|
|uuid|string|Chrome plugin unique identifier|
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

