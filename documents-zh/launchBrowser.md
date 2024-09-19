### 基础信息

> GET /api/v2/browser/start

接口描述：用于启动环境对应的浏览器，需要指定环境ID，启动成功后可以获取浏览器debug接口用于执行 `selenium` 和 `puppeteer`自动化。 `Selenium` 需要使用到对应内核版本匹配的 `Webdriver`。启动浏览器后可在返回值中拿到对应的 `Webdriver` 的路径。

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :-- | :-- | :-- | :-- | :-- |
| account_id | 环境ID，环境导入成功后生成的唯一ID | string | 是 | | |
| headless | 是否无头浏览器 | number | 否  | 不传:否 1:是 | 不传 |

### 请求示例
```
http://localhost:50213/api/v2/browser/start?account_id=d03ca5de08ec8e02c4b78558ee84d7fc
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 -6:未实名认证 | |
| msg  | 返回成功或者失败消息 | string | | |
| data | 返回数据 | object | | |

`data`结构体配置
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| debuggingPort | 测试端口 | string | | |
| webdriver | 浏览器程序位置 | string | | |
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
        "ws":{
            "selenium":"127.0.0.1:xxxx",
            "puppeteer":"ws://127.0.0.1:xxxx/devtools/browser/xxxxxx"
        },
        "debuggingPort":"xxxx",
        "webdriver":"C:\xxxx\chromedriver.exe"
    },
    "msg":"success"
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

