### 基础信息

> POST /api/v2/userapi/cookie/upsert

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| shopid | 环境id | string | 是   | | |
| cookies | 标准cookie格式 | `cookies` | 是   | | |


`cookies` 结构体配置：

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| name | 名称 | string | 是 | | |
| value | 值 | string | 是 | | |
| domain | 有效域 | string | 是 | | |
| expirationDate | 有效期 | number | 是 | | |
| hostOnly | 域名完全匹配 | boolean | 是 | | |
| httpOnly | 避免cookie被Javascript访问 | boolean | 是 | | |
| path | 路径 | string | 是   | | |
| sameSite | 限制第三方 Cookie | string | 是 | Strict:完全禁止 Lax:get请求除外 None:允许所有,必须同时设置Secure属性 | |
| secure | 安全属性 | boolean | 是 | | |
| session |     | boolean | 是 | | |
| storeId |     | string | 是 | | |
| port | 端口 | int | 是 | | |

### 请求示例

```
http://localhost:50213/api/v2/userapi/cookie/upsert
```

### 请求体

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
