### 基礎資訊

> POST /api/v2/userapi/group/list

### 請求參數
|參數名稱|類型|必填|說明|
|:------- |:----- |:----|:------ |
| group | string |否|分組名模糊|
| offer | int |是|從第offer條開始計算（offer最小是0）|
| number | int |是|需要選取的條數（最大不超過20）|

### 請求示例

```
http://localhost:50213/api/v2/userapi/group/list
```

### 請求體

```json
{
    "group": "xxx",
    "offer": 1,
    "number": 20
}
```

### 返回數據

|參數名稱|類型|說明|
|:------- |:----- |:-------------------------- |
| code | string |執行狀態碼0成功-1輸入格式錯誤-2獲取數量异常-4帳號登入异常|
| msg | string |返回成功或者失敗消息|
|name|string|分組名|
|gropid|string|分組ID|

執行成功

```json
{
  "code":0,
  "msg":"Success",
  "data":{
    "group":[
      {
      "name":"指紋瀏覽器測試分組-1",
      "gropid":"fdrgdgsfgsertgreaay34575422"
      },
      {
      "name":"指紋瀏覽器測試分組-2",
      "gropid":"fd2rgdgsfgsert3reaa44575424"
      }
    ]
  }
}
```

執行失敗

```json
{
    "code": -2,
    "msg": "fail message",
    "data": {
        "group": null
    }
}
```