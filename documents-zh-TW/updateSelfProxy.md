### 基礎資訊

> POST /api/v2/userapi/selfproxy/update

### 請求參數

`proxy` 結構體數組，要配寘的參數資訊（詳見：proxy）

`proxy` 結構體配寘：

| 參數名稱 | 類型 | 必填 | 說明 |
| :-------- | :----- | :--- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| deviceid      | string | 是   | 代理id |
| name      | string | 否   | 代理名稱  如果傳空表示不修改 |
| proxytype | int | 否   | 代理類型  如果傳0表示不修改1：有用戶名密碼sock5協定3:無用戶名密碼socks5協定4:http協定5:https協定6:http有用戶名密碼協定7:https有用戶名密碼協定 |
| proxyaddr | string | 否   | 代理地址  如果傳空表示不修改 |
| proxyu    | string | 否   | 登入帳號  如果傳空表示不修改 |
| proxyp    | string | 否   | 登入密碼  如果傳空表示不修改 |
| notes    | string | 否   | 備註  如果傳空表示不修改 |


### 請求示例

```
http://localhost:50213/api/v2/userapi/selfproxy/update
```

### 請求體

```json
{
    "proxy": {
        "name": "代理修改",
        "proxytype": 0,
        "proxyaddr": "",
        "deviceid": "XXXX5e1663e3efcb05e66XXXXc",
        "notes": "修改",
        "proxyu": "99999",
        "proxyp": "55555"
    }
}
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