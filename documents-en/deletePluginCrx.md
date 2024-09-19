### Basic information

> DELETE /api/v2/plugin/open/deletePluginCrx

Interface description: Delete uploaded plugins, Body application/JSON request

### Request parameters

```json
{
  "pluginId": ""
}
```

|Parameter Name|Type|Required|Explain|
|:----| :-- | :-- | :--- |
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

