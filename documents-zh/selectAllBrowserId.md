### 基础信息

> POST /api/v2/userapi/user/shopidlist

### 请求参数
无

### 请求示例
```
http://localhost:50213/api/v2/userapi/user/shopidlist
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 | |
| msg  | 返回成功或者失败消息 | string | | |
| shopIds | 返回的环境列表id | []string | | |

执行成功

```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "shopIds": [
            "bfd0b654a605f9d53e5a5cdac939d74",
            "fbd2bc962b08518cb6be1acb8ef00",
            "b0d6326c9f05c91dccb72e59f083",
            "0d5fcf6d3df35b2bbfcdd5abd8b9",
            "24b6eed92e3a88e8d7f5a71ab0dc",
            "a75e5c7346650f4baa1cc8176e613",
            "a3c9a8923268f77637ef2cbd4a1e7"
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
