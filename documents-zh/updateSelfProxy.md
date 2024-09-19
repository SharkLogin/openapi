### 基础信息

> POST /api/v2/userapi/selfproxy/update

### 请求参数

`proxy` 结构体数组，要配置的参数信息（详见：proxy）

`proxy` 结构体配置：

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| deviceid  | 代理id | string | 是   | | |
| name      | 代理名称 如果传空表示不修改 | string | 否   | | |
| proxytype | 代理类型 | int | 否   | 0:表示不修改  1:有用户名密码sock5协议 3:无用户名密码socks5协议 4:http协议 5:https协议 6:http有用户名密码协议 7:https有用户名密码协议 | |
| proxyaddr | 代理地址 如果传空表示不修改 | string | 否   | | |
| proxyu    | 登录账号 如果传空表示不修改 | string | 否   | | |
| proxyp    | 登录密码 如果传空表示不修改 | string | 否   | | |
| notes     | 备注 如果传空表示不修改 | string | 否   | | |
                                                                                                
### 请求示例

```
http://localhost:50213/api/v2/userapi/selfproxy/update
```

### 请求体

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

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 | |
| msg  | 返回成功或者失败消息 | string | | |

执行成功

```json
{
    "code": 0,
    "msg": "Success"
}
```

执行失败

```json
{
    "code": -1,
    "msg": "fail message"
}
```

