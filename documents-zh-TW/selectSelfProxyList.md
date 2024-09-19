### 基礎資訊

> POST /api/v2/userapi/selfproxy/list

### 請求參數

| 參數名稱 | 類型 | 必填 | 說明 |
| :-------- | :----- | :--- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| page | int | 是   | 頁碼          |
| pageSize    | int | 是   | 每頁大小       |
| name    | string | 否   | 代理名稱      |

### 請求示例

```
http://localhost:50213/api/v2/userapi/selfproxy/list
```  

### 請求體

```json
{
    "page": 1,
    "pageSize": 10,
    "name": ""
}
```

### 返回數據

| 參數名稱 | 類型 | 說明                                                            |
| :------- | :----- | :---------------------------------------------------------------- |
| code     | int    | 0成功-1輸入格式錯誤-2服務异常-4帳號登入异常 |
| msg      | string | 返回成功或者失敗消息                                    |
| deviceid      | string | 设备id |
| companyid      | string | 團隊id |
| name      | string |  代理名稱  |
| proxytype | int | 代理類型1：有用戶名密碼sock5協定3:無用戶名密碼socks5協定4:http協定5:https協定6:http有用戶名密碼協定7:https有用戶名密碼協定 |
| proxyaddr | string |  代理地址          |
| user    | string | 登入帳號        |
| passwd    | string |  登入密碼         |
| notes    | string |  備註             |
| createdat    | string |  創建時間          |

執行成功

```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "list": [
            {
                "deviceid": "cc12c5e1663e3efcb05e66088XX",
                "companyid": "e9b455594c05b52210226XX",
                "name": "代理修改",
                "proxyaddr": "1.1.1.1:2333",
                "proxytype": 1,
                "user": "99999",
                "passwd": "55555",
                "notes": "修改1",
                "createdat": "2024-04-12 15:58:06"
            }
        ],
        "total": 1,
        "pageSize": 10,
        "currentPage": 1
    }
}
```

執行失敗

```json
{
    "code": -1,
    "msg": "fail message"
}
```


