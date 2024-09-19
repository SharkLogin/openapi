### 基础信息

> POST /api/v2/userapi/selfproxy/list

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| page | 页码 | int | 是   | | |
| pageSize | 每页大小 | int | 是   | | |
| name | 代理名称 | string | 否   | | |

### 请求示例

```
http://localhost:50213/api/v2/userapi/selfproxy/list
```  

### 请求体

```json
{
    "page": 1,
    "pageSize": 10,
    "name": ""
}
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 | |
| msg  | 返回成功或者失败消息 | string | | |
| deviceid | 代理id | string | | |
| companyid | 团队id | string | | |
| name | 代理名称  | string | | |
| proxytype | 代理类型 | int | 1:有用户名密码sock5协议 3:无用户名密码socks5协议 4:http协议 5:https协议 6:http有用户名密码协议 7:https有用户名密码协议 | |
| proxyaddr | 代理地址 | string | | |
| user | 登录账号 | string | | |
| passwd | 登录密码 | string | | |
| notes | 备注 | string | | |
| createdat | 创建时间 | string | | |

执行成功

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

执行失败

```json
{
    "code": -1,
    "msg": "fail message"
}
```

