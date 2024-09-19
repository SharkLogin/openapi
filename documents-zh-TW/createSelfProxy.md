### 基礎資訊

> POST /api/v2/userapi/selfproxy/create

### 請求參數

`proxy` 結構體數組，要配寘的參數資訊（詳見：proxy）

`proxy` 結構體配寘：

| 參數名稱 | 類型 | 必填 | 說明 |
| :-------- | :----- | :--- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name      | string | 是   | 代理名稱 |
| proxytype | int | 是   | 代理類型1：有用戶名密碼sock5協定3:無用戶名密碼socks5協定4:http協定5:https協定6:http有用戶名密碼協定7:https有用戶名密碼協定 |
| proxyaddr | string | 是   | 代理地址             |
| proxyu    | string | 否   | 登入帳號         |
| proxyp    | string | 否   | 登录密码         |
| notes    | string | 否   | 備註                |

### 請求示例

```
http://localhost:50213/api/v2/userapi/selfproxy/create
```

### 請求體

```json
{
    "proxy": {
        "name": "代理1",
        "proxytype": 1,
        "proxyaddr": "1.1.1.1:2333",
        "proxyp": "7777777",
        "proxyu": "8888888",
        "notes": "代理"
    }
}
```

### 返回數據

| 參數名稱 | 類型   | 說明                                         |
| :------- | :----- | :------------------------------------------- |
| code     | int    | 0 成功-1輸入格式錯誤-2服務异常-4帳號登入异常 |
| msg      | string | 返回成功或者失敗消息                         |

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

