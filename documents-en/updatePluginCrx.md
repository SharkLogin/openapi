### Basic information

> PUT /api/v2/plugin/open/updatePluginCrx

Interface description: Edit plugin form, Body application/JSON request

### Request parameters

```json
{
  "name": "",
  "icon": "",
  "file": "",
  "brief": "",
  "uuid": "",
  "pluginId": "",
  "imgs": []
}
```

|Parameter Name|Type|Required|Explain|
|:----| :-- | :-- | :--- |
| pluginId | string | Yes | Plugin ID |
| name | string | Yes | name |
| icon | string | No | icon |
| file | string | No | file address |
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

