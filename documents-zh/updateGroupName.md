### 基础信息

> POST /api/v2/userapi/group/update

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :-- | :--- | :--- | :---- | :---- |
| groupid | 分组ID | string | 是 | | |
| name  | 分组名称 | string | 否 | 2到40个长度字符 | |

### 请求示例
```
http://localhost:50213/api/v2/userapi/group/update
```

### 请求体
```json
{
    "groupid":"9d19597b113ac7ed81225af48c364881",
    "name":"分组测试"
}
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:分组名称太长或者太短 -4:账号登录异常 | |
| msg | 返回成功或者失败消息 | string | | |

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
    "code": -2,
    "msg": "fail message",
}
```