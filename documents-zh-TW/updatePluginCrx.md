### 基礎資訊

> PUT /api/v2/plugin/open/updatePluginCrx

介面描述：編輯挿件表單，Body application/json請求

### 請求參數

|參數名稱|類型|必填|說明|
|:----| :-- | :-- | :--- |
| pluginId | string | 是 | 挿件ID |
| name | string | 是 | 名稱 |
| icon | string | 否 | 圖標 |
| file | string | 否 | 檔案地址 |
| brief | string | 否 | 簡介 |
| uuid | string | 否 | chrome挿件唯一標識 |
| imgs | []string | 否 | 輪播圖 |

### 請求示例

```
http://localhost:50213/api/v2/plugin/open/updatePluginCrx
```
### 請求體

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

