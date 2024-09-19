### 基礎資訊

> GET /api/v2/plugin/open/findPluginCompanies

介面描述：挿件分配的環境，需要先調用分配環境提交表單介面（/api/v2/plugin/open/bind），獲取當前挿件綁定的環境

### 請求參數

|參數名稱|類型|必填|說明|
|:----| :-- | :-- | :--- |
| pluginId | string | 是 | 挿件ID |

### 請求示例

```
http://localhost:50213/api/v2/plugin/open/findPluginCompanies?pluginId=bd4d0392c2b4455da6b1ba99a127825a
```

### 返回數據

|參數名稱|類型|說明|
|:----| :-- | :-- |
|accountIds|[]string|分配的環境ID清單|
|companyId|string|企業ID|
|pluginId|string|挿件ID|
|pluginName|string|挿件名稱|
|pluginCompanyId|string|唯一標識|

執行成功

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
  "msg": "操作成功",
  "requestId": ""
}
```

執行失敗

```json
{
  "code": 30008,
  "data": {},
  "msg": "獲取失敗",
  "requestId": ""
}
```

