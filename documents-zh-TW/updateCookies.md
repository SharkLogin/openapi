### 基礎資訊

> POST /api/v2/userapi/cookie/upsert

### 請求參數

| 參數名稱 | 類型 | 必填 | 說明 |
| :-------- | :----- | :--- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| shopid      | string | 是   | 環境id |
| cookies      | `cookies` | 是   | 標準cookie格式 |


`cookies` 结构体配置：

| 參數名稱 | 類型 | 必填 | 說明 |
| :-------- | :----- | :--- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| domain      | string | 是   |  |
| expirationDate      | number | 是   |  |
| hostOnly      | boolean | 是   |  |
| httpOnly      | boolean | 是   |  |
| path      | string | 是   |  |
| sameSite      | string | 是   |  |
| secure      | boolean | 是   |  |
| session      | boolean | 是   |  |
| storeId      | string | 是   |  |
| value      | string | 是   |  |
| port      | int | 是   |  |

### 請求示例

```
http://localhost:50213/api/v2/userapi/cookie/upsert
```

### 請求體

```json
{
    "shopid": "900bc9bc9438f96654006add8e7d344b",
    "cookies": [
        {
            "domain": ".XXX.cn",
            "hostOnly": false,
            "httpOnly": false,
            "name": "Hm_lpvt_a73626d29XXX",
            "path": "/",
            "sameSite": "",
            "secure": false,
            "session": false,
            "storeId": "",
            "value": "1711004434",
            "port": 443
        }
    ]
};
```

### 返回數據

| 參數名稱 | 類型   | 說明                                        |
| :------- | :----- | :------------------------------------------ |
| code     | int    | 0成功-1輸入格式錯誤-2服務异常-4帳號登入异常 |
| msg      | string | 返回成功或者失敗消息                        |

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
    "code": -1,
    "msg": "fail message"
}
```

