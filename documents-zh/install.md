### 基础信息

> POST /api/v2/plugin/open/install

接口描述：企业授权安装插件，Body application/json 请求

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| pluginId | 插件ID | string | 是 | | |


### 请求示例

```
http://localhost:50213/api/v2/plugin/open/install
```

### 请求体
```json
{
  "pluginId": "bd4d0392c2b4455da6b1ba99a127825a"
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

