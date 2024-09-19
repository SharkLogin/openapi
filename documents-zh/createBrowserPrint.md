### 基础信息

> POST /api/v2/userapi/user/create

### 请求参数

`browser` 结构体数组，要配置的参数信息（详见：browser）

`browser` 结构体数组，格式如下：

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| name     | 浏览器名称                        |string | 是 | | |
| proxy    | 代理信息（详见`proxy`配置）        | object | 是 | | |
| accounts | 账号相关信息（详见`accounts`配置） | object | 否 | | |
| finger   | 浏览器指纹信息（详见`finger`配置） | object | 否 | | |

`proxy` 结构体配置：

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| type | 代理类 | string | 是 | official:平台代理列表的、self:自有代理列表的、socks5、http、https、local:本地 | |
| uuid | 代理ID号,当type是official或者是self的时候填写这选项标识代理的唯一标识可以从UI界面的平台代理盒自由代理中查看 | string | 否 | | |                                                   |
| public_ip | 你的代理公网出口 IP 用于定位使用的 IP，如果为空会无法进行 IP 定位择优配置浏览器指纹信息 | string | 否 | | |                                                                                 |
| socks5 | 代理信息 当 type 设置为 socks5 时设置这个选项（详见 `socks5` 配置） | object | 否 | | |
| http | 代理信息 当 type 设置为 http 时设置这个选项（详见`http` 配置） | object | 否 | | |
| https | 代理信息 当 type 设置为 https 时设置这个选项（详见 `https` 配置） | object | 否 | | |
| product | 代理信息 当 type 设置为 official 时设置这个选项 | int | 否 | 0:无 1:云平台 2:家庭宽带, 3:国内动态 4:海外动态 | 0 |

`socks5` 结构体配置：

| 参数   | 说明     | 类型   | 必填 | 可选值 | 默认值 |
| :----- | :------ | :----- | :--- | :---- | :----- |
| Addr   | 代理地址 | string | 是   |       |        |
| User   | 用户名   | string | 否   |       |        |
| Passwd | 密码     | string | 否   |       |        |

`http` 结构体配置：

| 参数   | 说明     | 类型   | 必填 | 可选值 | 默认值 |
| :----- | :------ | :----- | :--- | :---- | :----- |
| Addr   | 代理地址 | string | 是   |       |        |
| User   | 用户名   | string | 否   |       |        |
| Passwd | 密码     | string | 否   |       |        |

`https` 结构体配置：

| 参数   | 说明     | 类型   | 必填 | 可选值 | 默认值 |
| :----- | :------ | :----- | :--- | :---- | :----- |
| Addr   | 代理地址 | string | 是   |       |        |
| User   | 用户名   | string | 否   |       |        |
| Passwd | 密码     | string | 否   |       |        |

`accounts ` 结构体配置：

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| openurls | 浏览器打开时访问的 url 地址 | []string | 否 | | |
| groupid  | 分组 ID 创建的新指纹环境分组到指定的位置 | string | 否 | | |
| user     | 平台账号 要自动登录的 url 环境账号 | string | 否   | | |
| passwd   | 平台账号的密码 要自动登录的 url 环境密码 | string | 否 | | |
| cookie   | 要打开环境的 cookie ,  账号和 cookie 不能同时填写，此字段值为空时表示不存储cookie数据，如果需要同步cookie, 此字段必填, 请传"[]" | string | 否 | |  |

`finger `结构体配置：

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| kernelversion  | kernelversion 浏览器内核大版本号 | string | 否 | 107，119，122 | 107 |
| UaVersion      | 浏览器大版本号 | int | 否 | 目前支持 100-117 不传自动生成 | |
| System         | 操作系统版本 | string | 否  | 目前支持（Windows 7、Windows 8、Windows 8.1、Windows 10、Windows 11、IOS 14、IOS 15、IOS 16、Android 9、Android 10、Android 11、Android 12、Android 13、MacOS 10、MacOS 11、MacOS 12、MacOS 13) 不传会自动生成All Windows, "All Windows":是在所有支持的Windows操作系统中自动生成;  "All IOS":在所有支持的IOS系统中生成;  "All Android":在所有Android系统中随机 All MacOS:在所有MacOS中随机。 | |
| UserAgent      | UserAgent 不写根据系统和浏览器版本自动生成 | string | 否 | | |
| Language       | 浏览器的语言 不传会根据代理 IP 地址自动生成 详细看支持的语言详细列表(如果是使用动态 IP 自动生成为中文) | []string | 否 | | |
| Zone           | 时区 不传会根据代理 IP 地址自动生成 详细查看时区支持的列表(如果是使用动态 IP 自动生成为北京时间) | string | 否 | | |
| DPI            | 平面分辨率 | string | 否 | 分隔符x(示例:1920x1080),空自动生成 | 默认 |
| FontList       | 字体列表 不传系统自动生成 | []string | 否 | | |
| WebRTC         | Chrome 即时通信组件 | int | 否 | 0:禁用,网站会拿不到IP 1:真实,网站会获取真实IP 2:替换,使用代理IP覆盖真实IP 3:转发,IP代理场景使用 | 0 |
| WebRTCIP       | 内网ip；WebRTC设置为2时配置 | string | 否 | | |
| Canvas         | 浏览器canvas指纹开关 | int | 否 | 0:倾向一致性 1:关闭 2:倾向随机性 | 0 |
| WebGl          | 浏览器webgl元数据指纹开关| int | 否 | 1:隐身 2:真实 | 1 |
| AudioContext   | 音频流 | int | 否 | 1:隐身 2:真实 | 1 |
| SpeechVoices   | SpeechVoices指纹 | int | 否 | 1:每个浏览器使用当前电脑默认的SpeechVoices 2:添加相应的噪音，同一电脑上为每个浏览器生成不同的SpeechVoices | 1 |
| MediaDevice    | 媒体设备开关 | int | 否 | 1:关闭（每个浏览器使用当前电脑默认的媒体设备id）2:启用（使用相匹配的值代替您真实的媒体设备ID，噪声）| 1 |
| Cpu            | CPU 核心数量 不传会自动生成 | int | 否 | | |
| Mem            | 内存参数 不传会自动生成 | float64  | 否 | | |
| DeviceName     | 计算机名 | string | 否 | 15个字符长度以内, 不传会自动生成 | |
| Mac            | MAC 地址 不传会自动生成 | string | 否 | | |
| Hardware       | 硬件加速 | int | 否 | 0:关闭 1:开启 2:默认 | 1 |
| Bluetooth      | 蓝牙 | int | 否 | 0:关闭 1:开启 | 0 |
| DoNotTrack     | “请勿跟踪”浏览器设置 | int | 否 | 1:不启用 2:启用 3:默认 | 1 |
| EnableScanPort | 端口扫描防护 | int | 否 | 1:开启 2:关闭 | 1 |
| ScanPort       | 白名单 0~65535 关闭状态不写 当 EnableScanPort 是 1 时这里为空会自动生成本地端口 | []int | 否 | | |
| geographic     | 地理位置 （默认使用 IP 定位 动态代理 IP 不支持次选项为禁止） | object | 否 | | |

`geographic` 结构体配置：

| 参数 | 说明 | 类型 | 必填 | 可选值 | 默认值 |
| :--- | :--- | :-- | :--- | :---- | :----- |
| enable    | 地理位置设置 | int    | 否   | 1:启用 2:询问 3:禁止 | 1 |
| user      | 定位方式     | int    | 否   |  1:使用ip定位 2:自定义 | 1 |
| longitude | 经度(当enable等于2且UseIP等于0时使用) | string | 否   | -180 - 180 | |
| latitude  | 纬度(当enable等于2且UseIP等于0时使用) | string | 否   | -90 - 90 | |
| accuracy  | 精度（米）(当enable等于2且UseIP等于0时使用) | string | 否   | 10 - 5000 | |

### 请求示例
```
http://localhost:50213/api/v2/userapi/user/create
```

### 请求体

```json
{
  "browser": [
    {
      "name": "指纹浏览器",
      "proxy": {
        "uuid": "",
        "public_ip": "",
        "type": "https",
        "https": {
          "Addr": ""
        }
      },
      "accounts": {
        "openurls": ["www.baidu.com"],
        "groupid": "",
        "cookie": "",
        "passwd": "123456",
        "user": "zhanghao"
      },
      "finger": {
        "kernelversion": "107",
        "UAversion": 107,
        "System": "windows 10",
        "UserAgent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.6237.0 Safari/537.36",
        "Language": [],
        "Zone": "",
        "DPI": "随机",
        "FontList": [],
        "WebRTCIP": "",
        "Canvas": 2,
        "WebGl": 1,
        "WebGLVendor": "Google Inc. (NVIDIA)",
        "AudioContext": 1,
        "SpeechVoices": 1,
        "MediaDevice": 1,
        "Cpu": 8,
        "Mem": 2,
        "DeviceName": "",
        "Mac": "",
        "Hardware": 1,
        "Bluetooth": 1,
        "DoNotTrack": 1,
        "EnableScanPort": 1,
        "ScanPort": [155],
        "geographic": {
          "enable": 1,
          "useip": 1
        }
      }
    }
  ]
}
```

### 返回数据

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| :--- | :-- | :--- | :----- | :---- |
| code | 执行状态码 | int | 0:成功 -1:输入格式错误 -2:获取数量异常 -4:账号登录异常 | |
| msg  | 返回成功或者失败消息 | string | | |
| name | 窗口名称接口自你传的 | string | | |
| id   | 新的指纹窗口 id | string | | |

执行成功

```json
{
  "code": 0,
  "msg": "Success",
  "data": {
    "browse": [
      { 
        "id": "1b9f203c9d989a602e52fe1e1eb65025", 
        "name": "指纹浏览器" 
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
        "browse": null
    }
}
```