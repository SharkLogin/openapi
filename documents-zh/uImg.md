### 基础信息

> POST /api/v2/plugin/open/uImg

接口描述：单图片上传

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| file | 上传的文件，postForm请求 | 文件 | 是 | | |

### 请求示例

```
http://localhost:50213/api/v2/plugin/open/uImg
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| tag | 文件格式 | string | | |
| name | 名称 | string | | |
| url | 文件地址 | string | | |


执行成功

```json
{
  "code": 200,
  "data": {
    "crx": {
      "name": "",
      "url": "",
      "tag": ""
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

