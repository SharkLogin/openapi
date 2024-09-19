### 基礎資訊

> POST /api/v2/userapi/group/update

### 請求參數

|參數名稱|類型|必填|說明|
|:------- |:----- |:--- |:------- |
| groupid | string |是|分組ID |
| name | string |否|分組名稱（2到40個字元長度）|

### 請求示例
```
http://localhost:50213/api/v2/userapi/group/update
```

### 請求體
```json
{
    "groupid":"9d19597b113ac7ed81225af48c364881",
    "name":"分組測試"
}
```

### 返回數據

|參數名稱|類型|說明|
|:------- |:----- |:--- |
| code | int |執行狀態碼0成功-1輸入格式錯誤-2分組名稱太長或者太短-4帳號登入异常|
|msg|string|返回成功或者失敗消息|

執行成功

```json
{
  "code": 0,
  "msg": "Success"
}
```

執行失敗

```json
{
    "code": -2,
    "msg": "fail message",
}
```