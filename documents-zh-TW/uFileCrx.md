### 基礎資訊

> POST /api/v2/plugin/open/uFileCrx

介面描述：上傳挿件-附件

### 請求參數

|參數名稱|類型|必填|說明|
|:----| :-- | :-- | :--- |
| file | 文件 | 是 | 上傳的檔案，postForm請求 |

### 請求示例

```
http://localhost:50213/api/v2/plugin/open/uFileCrx
```

### 返回數據

||類型|說明|
|:----| :-- | :-- |
|tag|string|檔案格式|
|uuid|string|chrome挿件唯一標識|
|name|string|名稱|
|url|string|檔案地址|

執行成功

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

