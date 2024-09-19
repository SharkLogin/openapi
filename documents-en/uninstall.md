### Basic information

> DELETE /api/v2/plugin/open/uninstall

Interface Description: To cancel the authorization installation of plugins for enterprises, it is necessary to first call the enterprise authorization installation plugin (/API/v2/plugin/open/install), and request Body application/JSON

### Request parameters

```json
{
  "pluginCompanyId": ""
}
```

|Parameter Name|Type|Required|Explain|
|:----| :-- | :-- | :--- |
| pluginCompanyId | string | Yes | Unique identifier, returned by the plugin assigned account/API/v2/plugin/open/findPluginCompanies interface |

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

