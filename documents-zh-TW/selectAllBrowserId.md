### 基礎資訊

> POST /api/v2/userapi/user/shopidlist

### 請求參數
無

### 請求示例
```
http://localhost:50213/api/v2/userapi/user/shopidlist
```

### 返回數據

|參數名稱|類型|說明|
|:-------- |:------ |:----------------------- |
| code | int | 0成功-1輸入格式錯誤-2査詢异常-4帳號登入异常|
| msg | string |返回成功或者失敗消息|
| shopIds | []string |返回的環境清單id |

執行成功
```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "shopIds": [
            "bfd0b654a605f9d53e5a5cdac939d74",
            "fbd2bc962b08518cb6be1acb8ef00",
            "b0d6326c9f05c91dccb72e59f083",
            "0d5fcf6d3df35b2bbfcdd5abd8b9",
            "24b6eed92e3a88e8d7f5a71ab0dc",
            "a75e5c7346650f4baa1cc8176e613",
            "a3c9a8923268f77637ef2cbd4a1e7"
        ]
    }
}
```

執行失敗

```json
{
    "code": -1,
    "msg": "fail message",
    "data": {}
}
```