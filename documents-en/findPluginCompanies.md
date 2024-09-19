### Basic information

> GET /api/v2/plugin/open/findPluginCompanies

Interface Description: The account assigned by the plugin needs to first call the account submission form interface (/API/v2/plugin/open/bind) to obtain the account bound by the current plugin

### Request parameters

|Parameter Name|Type|Required|Explain|
|:----| :-- | :-- | :--- |
| pluginId | string | Yes | Plugin ID |

Execution successful

```json
{
  "code": 200,
  "data": {
    "repluginCompanies": {
      "accountIds": [],
      "companyId": "",
      "pluginId": "",
      "pluginName": "",
      "pluginCompanyId": ""
    }
  },
  "msg": "Operation successful",
  "requestId": ""
}
```

|Parameter Name|Type|Explain|
|:----| :-- | :-- |
|accountIds|[]string|List of assigned account IDs|
|companyId|string|Enterprise ID|
|pluginId|string|Plugin ID|
|pluginName|string|Plugin Name|
|pluginCompanyId|string|Unique identifier|

Execution failed

```json
{
  "code": 30008,
  "data": {},
  "msg": "Acquisition failed",
  "requestId": ""
}
```

