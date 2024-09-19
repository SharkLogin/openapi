### 基础信息

> POST /api/v2/userapi/group/list

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| group | 分组名模糊 | string | 否 |  | |
| offer | 从第offer条开始计算 | int | 是 | offer最小是0 | |
| number | 需要提取的条数 | int | 是 | 最大不超过20 | |

### 请求示例

```
http://localhost:50213/api/v2/userapi/group/list
```

### 请求体

```json
{
    "group": "xxx",
    "offer": 1,
    "number": 20
}
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 | |
| msg  | 返回成功或者失败消息 | string | | |
| name | 分组名 | string | | |
| gropid | 分组ID | string | | |

执行成功

```json
{
    "code":0,
    "msg":"Success",
    "data":{
        "group":[
            {
                "name":"指纹浏览器测试分组-1",
                "gropid":"fdrgdgsfgsertgreaay34575422"
            },
            {
                "name":"指纹浏览器测试分组-2",
                "gropid":"fd2rgdgsfgsert3reaa44575424"
            }
        ]
    }
}
```

执行失败

```json
{
    "code": -2,
    "msg": "fail message",
    "data": {
        "group": null
    }
}
```