### 基礎資訊

> POST /api/v2/userapi/user/shopseriallist

### 請求參數

無

### 請求示例

```
http://localhost:50213/api/v2/userapi/user/shopseriallist
```

### 返回數據

| 參數名稱 | 類型 | 說明                                |
| :-------- | :------ | :------------------------------------- |
| code     | int    | 0成功-1輸入格式錯誤-2査詢异常-4帳號登入异常 |
| msg      | string | 返回成功或者失敗消息        |
| shopId      | string | 返回的環境id         |
| serial      | int | 返回的環境序號         |

執行成功

```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "list": [
            {
                "shopId": "b2a354395c06b5e16e",
                "serial": 96
            },
            {
                "shopId": "ebf96c272b708c944ef1a16",
                "serial": 89
            },
            {
                "shopId": "e7fd6d69588b5de2dffdd3f2",
                "serial": 88
            },
            {
                "shopId": "d4a41c1f5329addd406c5b4",
                "serial": 10
            }
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


