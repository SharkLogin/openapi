### Basic information

> POST /api/v2/plugin/open/bind

Interface Description: To assign an account and submit a form, it is necessary to first call the enterprise authorization installation plugin interface (/API/v2/plugin/open/install), and request Body application/JSON

### Request parameters

```json
{
  "accountIds": [
    "-1",
    "xxx"
  ],
  "pluginId": ""
}
```

|Parameter Name|Type|Required|Explain|
|:----| :-- | :-- | :--- |
| accountIds | []string | Yes | Account ID, -1 identifies the workbench |
| pluginId | string | Yes | Plugin ID |

Execution successful

```json
{
  "code": 200,
  "data": "",
  "msg": "Operation successful",
  "requestId": ""
}
```

Execution failed

```json
{
  "code": 30008,
  "data": {},
  "msg": "Acquisition failed",
  "requestId": ""
}
```

