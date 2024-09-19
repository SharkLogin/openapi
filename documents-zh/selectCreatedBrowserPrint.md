### 基础信息

> POST /api/v2/userapi/user/list

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| browserid | 浏览器指纹窗口ID列表 | []string | 是 | | |

### 请求示例

```
http://localhost:50213/api/v2/userapi/user/list
```

### 请求体

```json
{
    "browserid":[
        "08638991e03d59ccb9d26571bae80427",
        "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    ]
}
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 | |
| msg  | 返回成功或者失败消息 | string | | |
| data | 返回数据 | object | | |

`apibrowser` 结构体数组：

| 参数      | 说明                            | 类型 | 可选值 | 默认值 |
| :-------- | :----------------------------- | :--- | :----- | :---- |
| Name      | 指纹浏览器的名称                 | string | | |
| browserid | 要修改浏览器窗口的ID号           | string | | |
| proxy     | 代理信息（详见`proxy`结构体配置） | object | | |
| accounts  | 详见`accounts`结构体配置         | object | | |

`proxy`结构体配置：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| type | 代理类型 | string | official（在我们官网购买的）、self(已经在自有代理列表的)、socks5、http、https、local（本地） | socks5 | |
| public_ip |ip地址 | string | | |
| uuid | 代理设备id | string | | |
| socks5 | socks5代理（详见`socks5`结构体配置） | object | | |
| http | http代理（详见`http`结构体配置） | object | | |
| https | https代理（详见`https`结构体配置） | object | | |
| zhima | zhima代理（详见`zhima`结构体配置） | object | | |

`socks5`结构体配置：

| 参数 | 说明     | 类型    | 可选值  | 默认值 |
| :--- | :------ | :------ | :----- | :---- |
| Addr | 代理地址 | string  |        |       |
| User | 用户名   | string  |        |       |
| Passwd | 密码   | string  |        |       |

`http` 结构体配置：

| 参数 | 说明     | 类型    | 可选值  | 默认值 |
| :--- | :------ | :------ | :----- | :---- |
| Addr | 代理地址 | string  |        |       |
| User | 用户名   | string  |        |       |
| Passwd | 密码   | string  |        |       |

`https` 结构体配置：

| 参数 | 说明     | 类型    | 可选值  | 默认值 |
| :--- | :------ | :------ | :----- | :---- |
| Addr | 代理地址 | string  |        |       |
| User | 用户名   | string  |        |       |
| Passwd | 密码   | string  |        |       |

`zhima`结构体配置：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| Url      | 提取地址 | string | | |
| Interval | 提取间隔 | number | | 0 |


`accounts`结构体配置：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| openurls | 浏览器打开时访问的其他url地址列表 | []string | | |
| groupid  | 分组ID                        | string | | |
| user     | 平台账号                      | string | | |
| passwd   | 平台密码                      | string | | |
| cookie   | 账号或者cookie不能同时填写    | string | | |

执行成功

```json
{
    "code":0,
    "msg":"Success",
    "data":{
        "apibrowser":[
            {
                "Name":"测试窗口-1",
                "browserid":"08638991e03d59ccb9d26571bae80427",
                "proxy":{
                    "type":"socks5",
                    "uuid": "9261f478874c45ac989acb3ae317cb76",
                    "public_ip": "",
                    "socks5":{
                        "Addr":"89.2.3.1",
                        "User":"admin",
                        "Passwd":"123456"
                    },
                    "http": {
                        "Addr": "",
                        "User": "",
                        "Passwd": ""
                    },
                    "https": {
                        "Addr": "",
                        "User": "",
                        "Passwd": ""
                    },
                    "zhima": {
                        "Url": "",
                        "Interval": 0
                    }
                },
                "accounts":{
                    "openurls":["www.baidu.com"],
                    "groupid":"23984yoefjsoiroi4wqdfa",
                    "user":"admin",
                    "passwd":"adminrest",
                    "cookie":"erjagprtgjuwhgr;asgjresoi"
                }
            },
            {
                "Name":"测试窗口-2",
                "browserid":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
                "proxy":{
                    "type":"socks5",
                    "uuid": "9261f478874c45ac989acb3ae317cb76",
                    "public_ip": "",
                    "socks5":{
                        "Addr":"89.2.3.1",
                        "User":"admin",
                        "Passwd":"123456"
                    },
                    "http": {
                        "Addr": "",
                        "User": "",
                        "Passwd": ""
                    },
                    "https": {
                        "Addr": "",
                        "User": "",
                        "Passwd": ""
                    },
                    "zhima": {
                        "Url": "",
                        "Interval": 0
                    }
                },
                "accounts":{
                    "openurls":["www.baidu.com"],
                    "groupid":"23984yoefjsoiroi4wqdfa",
                    "user":"admin",
                    "passwd":"adminrest",
                    "cookie":"erjagprtgjuwhgr;asgjresoi"
                }
            }
        ]
    }
}
```

执行失败

```json
{
    "code": -1,
    "msg": "fail message",
    "data": {
        "apibrowser": null
    }
}
```
