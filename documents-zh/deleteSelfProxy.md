### 基础信息

> POST /api/v2/userapi/selfproxy/delete

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| deviceid | 代理id | []string | 是 | | |
                        
### 请求示例

```
http://localhost:50213/api/v2/userapi/selfproxy/delete
```

### 请求体

```json
{
    "deviceid": [
        "9a8cc12c5e1663e3efcb05e6608869dc",
        "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
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

