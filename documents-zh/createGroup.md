### 基础信息

> POST /api/v2/userapi/group/create

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| name | 分组名称 | string | 是 | 2到40个长度字符 | |

### 请求示例

```
http://localhost:50213/api/v2/userapi/group/create
```
### 请求体

```json
{
    "name": "xxx"
}
```

### 返回数据

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| code | 执行状态码 | int |  0:成功 -1:输入格式错误 -2:分组名称太长或者太短 -3:这个组名已经创建了 -4:账号登录异常 | | |
| msg | 返回成功或者失败消息 | string | | |
| data | 返回数据 | object | | |

`data`结构体配置
| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| groupid | 新建的分组ID | string | | |
| group | 新建的分组名 | string | | |

执行成功

```json
{
    "code":0,
    "msg":"Success",
    "data":{
        "groupid":"fdrgdgsfgsertgreaay34575422",
        "group":"指纹浏览器测试分组"
    }
}
```

执行失败

```json
{
    "code": -1,
    "msg": "fail message",
    "data": {
        "groupid": "",
        "group": ""
    }
}
```
