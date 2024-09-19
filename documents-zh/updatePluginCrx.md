### 基础信息

> PUT /api/v2/plugin/open/updatePluginCrx

接口描述：编辑插件表单，Body application/json 请求

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| pluginId | 插件ID | string | 是 | | |
| name | 名称 | string | 是 | | |
| icon | 图标 | string | 否 | | |
| file | 文件地址 | string | 否 | | |
| brief | 简介 | string | 否 | | |
| uuid | chrome插件唯一标识 | string | 否 | | |
| imgs | 轮播图 | []string | 否 | | |

### 请求示例

```
http://localhost:50213/api/v2/plugin/open/updatePluginCrx
```
### 请求体

```json
{
  "name": "",
  "icon": "",
  "file": "",
  "brief": "",
  "uuid": "",
  "pluginId": "",
  "imgs": []
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

