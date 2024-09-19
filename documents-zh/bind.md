### 基础信息

> POST /api/v2/plugin/open/bind

接口描述：分配环境提交表单，需要先调用企业授权安装插件接口（/api/v2/plugin/open/install），Body application/json 请求

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| accountIds | 环境ID-1标识工作台 | []string | 是 | | |
| pluginId | 插件ID | string | 是 | | |

### 请求示例

```
http://localhost:50213/api/v2/plugin/open/bind
```

### 请求体

```json
{
  "accountIds": [
    "-1",
    "xxx"
  ],
  "pluginId": ""
}
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 200:成功 其他:异常 | |
| msg  | 返回成功或者失败消息 | string | | |

执行成功

```json
{
  "code": 200,
  "data": "",
  "msg": "操作成功",
  "requestId": ""
}
```

执行失败

```json
{
  "code": 30008,
  "data": {},
  "msg": "获取失败",
  "requestId": ""
}
```

