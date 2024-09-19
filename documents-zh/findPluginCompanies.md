### 基础信息

> GET /api/v2/plugin/open/findPluginCompanies

接口描述：插件分配的环境，需要先调用分配环境提交表单接口（/api/v2/plugin/open/bind），获取当前插件绑定的环境

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| pluginId | 插件ID | string | 是 | | |

### 请求示例

```
http://localhost:50213/api/v2/plugin/open/findPluginCompanies?pluginId=bd4d0392c2b4455da6b1ba99a127825a
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| accountIds | 分配的环境ID列表 | []string | | |
| companyId | 企业ID | string | | |
| pluginId | 插件ID | string | | |
| pluginName | 插件名称 | string | | |
| pluginCompanyId | 唯一标识 | string | | |

执行成功

```json
{
  "code": 200,
  "data": {
    "repluginCompanies": {
      "accountIds": [],
      "companyId": "",
      "pluginId": "",
      "pluginName": "",
      "pluginCompanyId": ""
    }
  },
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

