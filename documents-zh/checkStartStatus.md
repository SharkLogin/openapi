### 基础信息

> GET /api/v2/browser/status

接口描述：用于环境浏览器的启动状态，需要指定环境ID。

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| account_id | 环境ID，环境导入成功后生成的唯一ID | string | 是 | | |

### 请求示例

```
http://localhost:50213/api/v2/browser/status?account_id=d03ca5de08ec8e02c4b78558ee84d7fc
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 | |
| msg  | 返回成功或者失败消息 | string | | |
| data | 返回成功数据 | object | | |

`data`结构体配置
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| status | 浏览器状态 | string | "Active":浏览器已打开运行中 "Inactive":浏览器未打开 | |
| ws | websocket信息 | object | | |

`ws`结构体配置
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| selenium | 浏览器debug接口，可用于selenium自动化 | string | | |
| puppeteer | 浏览器debug接口，可用于puppeteer自动化 | string | | |

执行成功

```json
{
    "code":0,
    "data":{
        "status":"Active",
        "ws":{
            "selenium":"127.0.0.1:xxxx",
            "puppeteer":"ws://127.0.0.1:xxxx/devtools/browser/xxxxxx"
        }
    }
}
```


执行失败

```json
{
    "code":-1,
    "data":{},
    "msg":"failed"
}
```

