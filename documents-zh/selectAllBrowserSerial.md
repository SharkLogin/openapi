### 基础信息

> POST /api/v2/userapi/user/shopseriallist

### 请求参数

无

### 请求示例

```
http://localhost:50213/api/v2/userapi/user/shopseriallist
```

### 返回数据
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 | |
| msg  | 返回成功或者失败消息 | string | | |
| shopId | 返回的环境id | string | | |
| serial | 返回的环境序号 | int | | |

执行成功

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

执行失败

```json
{
    "code": -1,
    "msg": "fail message",
    "data": {}
}
```



