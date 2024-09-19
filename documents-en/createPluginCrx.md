### Basic information

> POST /api/v2/plugin/open/createPluginCrx

Interface description: Upload plugin, submit plugin form, Body application/JSON request

### Request parameters

```json
{
  "name": "",
  "icon": "",
  "file": "",
  "brief": "",
  "uuid": "",
  "imgs": []
}
```

|Parameter Name|Type|Required|Explain|
|:----| :-- | :-- | :--- |
| name | string | Yes | name |
| icon | string | No | icon |
| file | string | No | File address |
| brief | string | No | brief introduction |
| uuid | string | No | Chrome plugin unique identifier |
| imgs | []string | No | Carousel chart |

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

