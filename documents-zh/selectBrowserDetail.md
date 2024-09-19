### 基础信息

> POST /api/v2/userapi/user/shopdetaillist

### 请求参数

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| browserid | 浏览器指纹窗口ID | []string | 是 | | |

### 请求示例

```
http://localhost:50213/api/v2/userapi/user/shopdetaillist
```
### 请求体

```json
{
    "browserid": [
        "d03ca5de08ec8e02c4b78558ee84d7fc",
        "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    ]
}
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 | |
| msg  | 返回成功或者失败消息 | string | | |
| data | 返回成功数据 | object | | |
| browser | 浏览器指纹窗口列表 | []object | | |

`browser` 结构体数组：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| name      | 指纹浏览器的名称 | string | | |
| browserid | 要修改浏览器窗口的ID号 | string | | |
| notes      | 备注 | string | | |
| is_star_tag | 是否星标 | int | 1:星标 0:未星标 | 0 |
| serial      | 序号 | int | | |
| cookie      | cookie json字符串 | string | | |
| group      | 分组 详见`group`结构体配置 | object | | |
| label      | 标签 详见`label`结构体配置 | object | | |
| proxy     | 代理信息（详见`proxy`结构体配置） | object | | |
| accounts  | 详见`accounts`结构体配置 | object | | |
| fingerprint  | 详见`fingerprint`结构体配置 | object | | |

`group`结构体配置：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| name | 分组名 | string | | |
| groupid | 分组id | string | | |

`label`结构体配置：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| name | 标签名 | string | | |
| id   | 标签id | string | | |

`proxy`结构体配置：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| inlie | 代理类型 | string | official:代理类型 self:自有代理 official:官方代理 local:本地 general:通用代理  | local |
| uuid  | 设备ID | string | | |
| type | 协议类型 | string | http、https、socks5 | socks5 |
| product | inlie 设置为 official 时设置这个选项 | int | 0:无 1:云平台 2:家庭宽带, 3:国内动态 4:海外动态 | 0 |
| PublicIP | 您的代理公网出口 IP 用于定位使用的 IP，如果为空会无法进行 IP 定位择优配置浏览器指纹信息 | string | | |
| socks5   | socks5代理（详见`socks5`结构体配置） | object |  | |
| http   | http代理（详见`http`结构体配置） | object | | |
| https   | https代理（详见`https`结构体配置） | object | | |


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

`accounts`结构体配置：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| url | 浏览器打开时访问的其他url地址 | []string | | |
| name | 网址或者名称 | string | | |
| user | 平台账号 | string | | |
| passwd | 平台密码 | string | | |
| lock   | 锁定账号 | int | 1:锁定 0:不锁定 | 0 |
| enableself | 是否是用户自定义平台 | int | 0:平台提供的 1:用户自定义的 | 0 |
| loginurl | 平台提供的网站访问地址 | string | | |

`finger `结构体配置：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| kernel | 浏览器信息 | string | Chrome | Chrome |
| kernelversion | 浏览器内核版本 | string | 107，119，122 | 122 |
| UAversion | 浏览器本号 | int | | |
| system | 操作系统版本 | string | | |
| ua | UserAgent 信息 | string | | |
| language | 浏览器的语言 | []string | | |
| zone | 时区 | string | | |
| geographic | 地理位置 （详见`geographic`结构体配置） | object | | |
| dpi | 平面分辨率 | string | 分隔符x(示例:1920x1080) | 默认 |
| fontfinger | 字体列表 | int | 1 | 1 |
| font | 字体列表 | object(详见`font`结构体配置) | | |
| WebRTC | Chrome 即时通信组件 | int | 0:禁用,网站会拿不到IP 1:真实,网站会获取真实IP 2:替换,使用代理IP覆盖真实IP 3:转发,IP代理场景使用 | 0 |
| WebRTCIP | 内网ip；WebRTC设置为2时配置 | string | | |
| Canvas | 浏览器canvas指纹开关 | int | 0:倾向一致性 1:关闭 2:倾向随机性 | 0 |
| WebGl | 浏览器webgl元数据指纹开关 | int | 1:隐身 2:真实 | 1 |
| WebGlInfo | 根据WebGl生成 | int | 0:关闭 1:真实 2:自定义 3:自动生成 | 2 |
| WebGLVendor | 根据WebGl生成 | string | Google Inc. (Intel)、Google Inc. (AMD)、Google Inc. (NVIDIA) | Google Inc. (Intel) |
| WebGLRenderer | 根据WebGl生成 | string | | |
| AudioContext | 音频流 | int | 1:隐身 2:真实 | 1 |
| SpeechVoices | SpeechVoices指纹 | int | 1:每个浏览器使用当前电脑默认的SpeechVoices 2:添加相应的噪音，同一电脑上为每个浏览器生成不同的SpeechVoices | 1 |
| mediadevice | 媒体设备开关 | int | 1:关闭（每个浏览器使用当前电脑默认的媒体设备id）2:启用（使用相匹配的值代替您真实的媒体设备ID，噪声） | 1 |
| cpu | CPU 核心数量 | int | | |
| mem | 内存参数 | int | | |
| devicename | 计算机名 | string | | |
| mac | MAC 地址 | string | | |
| hardware | 硬件加速 | int | 0:关闭 1:开启 2:默认 | 1 |
| Bluetooth | 蓝牙 | int | 0:关闭 1:开启 | 0 |
| Donottrack | “请勿跟踪”浏览器设置 | int | 1:不启用 2:启用 3:默认 | 1 |
| battery | 电池 | int | 0:禁止 1:真实 | 1 |
| enablescanport |  端口扫描防护 | int | 1:开启 2:关闭 | 1 |
| scanport | 当EnableScanPort是1本地端口,白名单0~65535关闭状态不写 | string | | |
| enableCookie | Cookie共享设置 | int |  0:按用户 1:安环境 | 1 |
| enableopen | 多开设置 | int | 0:关闭 1:开启 2:跟随团队 | 1 |
| enablenotice | 网页通知 | int | 0:禁止通知 1:询问 | 1 |
| enablepic | 禁止加载图片 | int | 0:关闭 1:开启 2:跟随团队 | 0 |
| picsize | 图片大小 | string | | |
| Enablesound | 禁止播放声音 | int | 0:关闭 1:开启 2:跟随团队 | 0 |
| Enablevideo | 禁止加载视频 | int | 0:关闭 1:开启 2:跟随团队 | 0 |

`geographic` 结构体配置：

| 参数      | 说明        | 类型 | 可选值 | 默认值 |
| :-------- | :---------- | :--- | :----- | :---- |
| enable    | 地理位置设置 | int    | 1:启用 2:询问 3:禁止 | 1 |
| user     | 定位方式     | int    |  1:使用ip定位 2:自定义 | 1 |
| longitude | 经度(当enable等于2且UseIP等于0时使用) | string | -180 - 180 | |
| latitude  | 纬度(当enable等于2且UseIP等于0时使用) | string | -90 - 90 | |
| accuracy  | 精度（米）(当enable等于2且UseIP等于0时使用) | string | 10 - 5000 | |

`font`结构体配置：

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| enable | 字体保护 | int | 0:关闭 1:开启 | 1 |
| list | 字体列表当enable为0时设置,可选值往数组中添加 | []string | "Roboto","Tahoma","Google Sans","Helvetica","arial","default","sans-serif","serif","cursive","monospace"...  | ["Arial","Calibri","Cambria Math","Cambria","Candara","Comic Sans MS","Consolas","Constantia","Corbel","Courier New","Ebrima","Franklin Gothic","Gabriola","Georgia","Impact","Lucida Console","Lucida Sans Unicode","MS Gothic","MS PGothic","MV Boli","Malgun Gothic","Marlett","Microsoft Himalaya","Microsoft JhengHei","Microsoft New Tai Lue","Microsoft PhagsPa","Microsoft Sans Serif","Microsoft YaHei","Microsoft Yi Baiti","MingLiU-ExtB","Mongolian Baiti","PMingLiU-ExtB","Palatino Linotype","Segoe Print","Segoe Script","Segoe UI Symbol","Segoe UI","SimSun","SimSun-ExtB","Sylfaen","Trebuchet MS","Verdana","Webdings","Gadugi","Javanese Text","Microsoft JhengHei UI","Myanmar Text","Sitka Small","Yu Gothic","MS UI Gothic","Microsoft Tai Le","MingLiU_HKSCS-ExtB","Symbol","Segoe UI Emoji","Bahnschrift"] |



执行成功

```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "browser": [
            {
                "browserid": "608b78e0c121e262712eaeaba1aa98e1",
                "name": "云登浏览器_3",
                "notes": "",
                "group": {
                    "name": "",
                    "groupid": ""
                },
                "label": [
                    {
                        "id": "3d4d05c941167a6e083ed7361a4c2167",
                        "name": "14654"
                    }
                ],
                "is_star_tag": 0,
                "proxy": {
                    "name": "",
                    "inlie": "local",
                    "uuid": "",
                    "type": "",
                    "product": 0,
                    "PublicIP": "",
                    "socks5": {
                        "Addr": "",
                        "User": "",
                        "Passwd": ""
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
                    }
                },
                "serial": 0,
                "cookie": "[]",
                "accounts": {
                    "loginurl": "",
                    "enableself": 1,
                    "url": [],
                    "name": "https://www.bilibili.com/",
                    "user": "",
                    "passwd": "",
                    "lock": 0
                },
                "fingerprint": {
                    "kernel": "Chrome",
                    "kernelversion": "107",
                    "system": "Windows 10",
                    "nextsystem": {
                        "Android": "",
                        "MacOS": "",
                        "IOS": "",
                        "Linux": ""
                    },
                    "UAversion": "106",
                    "ua": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/106.0.5249.60 Safari/537.36",
                    "language": [],
                    "uilanguage": null,
                    "zone": "",
                    "geographic": {
                        "enable": 1,
                        "user": 1,
                        "longitude": "",
                        "latitude": "",
                        "accuracy": ""
                    },
                    "dpi": "默认",
                    "widowssize": "默认",
                    "font": {
                        "enable": 1,
                        "list": []
                    },
                    "fontfinger": 1,
                    "WebRTC": 0,
                    "WebRTCIP": "",
                    "Canvas": 0,
                    "WebGl": 1,
                    "WebGlInfo": 2,
                    "WebGLVendor": "Google Inc. (Intel)",
                    "WebGLRenderer": "ANGLE (Intel, Intel(R) UHD Graphics 620 Direct3D11 vs_5_0 ps_5_0, D3D11-27.20.100.8984)",
                    "AudioContext": 1,
                    "SpeechVoices": 1,
                    "mediadevice": 1,
                    "cpu": 12,
                    "mem": 4,
                    "devicename": "DESKTOP-fRMTued",
                    "mac": "8C-04-BA-87-2A-5E",
                    "hardware": 1,
                    "Bluetooth": 0,
                    "Donottrack": 1,
                    "battery": 1,
                    "enablescanport": 1,
                    "scanport": "",
                    "enableCookie": 1,
                    "enableopen": 1,
                    "enablenotice": 1,
                    "enablepic": 0,
                    "picsize": "",
                    "Enablesound": 0,
                    "Enablevideo": 0
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
        "browser": null
    }
}
```



