### 基礎資訊

> DELETE /api/v2/plugin/open/uninstall

介面描述：企業取消挿件授權安裝，需要先調用企業授權安裝外掛程式（/api/v2/plugin/open/install），Body application/json請求

### 請求參數

|參數名稱|類型|必填|說明|
|:----| :-- | :-- | :--- |
| pluginCompanyId | string | 是 | 唯一標識，（挿件分配的環境/api/v2/plugin/open/findPluginCompanies）介面返回 |

### 請求示例

```
http://localhost:50213/api/v2/plugin/open/uninstall
```

### 請求體

```json
{
  "pluginCompanyId": ""
}
```

### 返回數據

| 參數名稱 | 類型   | 說明     |
| :------- | :----- | :--- |
| code     | int    | 執行狀態碼 200:成功; 其他:異常 |
| msg      | string | 返回成功或者失敗消息  |

執行成功

```json
{
  "code": 200,
  "data": "",
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

