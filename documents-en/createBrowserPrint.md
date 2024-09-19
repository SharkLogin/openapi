### Basic information

> POST /api/v2/userapi/user/create

### Request parameters

`Browser ` Structure array, parameter information to be configured (see: browser)
`Browser ` structure array, with the following format:

|Parameter Name | Type | Required | Description|
|:------- |:----- |:--- |:------- |
|name | string | Yes | Browser name|
|proxy | object | yes | proxy information (see 'proxy' configuration for details)|
|accounts | object | no | Account related information (see 'accounts' configuration for details)|
|finger | object | no | browser fingerprint information (see 'finger' configuration for details)|

`Proxy ` structure configuration:

|Parameter Name | Type | Required | Description|
|:------- |:----- |:--- |:------- |
|Type | string | Yes | The proxy class has the following options: official (platform proxy list), self (self owned proxy list), socks5 (now added), http (now added), https (now added), local (local)|
|uuid | string | no | agent ID number. When the type is official or self, fill in this option to identify the unique identifier of the agent. This can be viewed from the platform agent box in the UI interface|
|Public_ip | string | No | Your proxy public network exit IP is used to locate the IP used. If it is empty, it will not be possible to perform IP localization and optimize the configuration of browser fingerprint information|
|Socks5 | object | no | proxy information Set this option when type is set to socks5 (see 'socks5' configuration for details)|
|Http | object | no | proxy information. Set this option when the type is set to http (see 'http' configuration for details)|
|Https | object | no | proxy information Set this option when the type is set to https (see 'https' configuration for details)|
|Product | int | No | Proxy Information Set this option when type is set to official|

`Socks5 ` Structure configuration:

|Parameter Name | Type | Required | Description|
|:-------- |:------ |:--- |:--------|
|Addr | string | Yes | Proxy address|
|User | string | No | User name|
|Passwd | string | No | Password|

`HTTP` structure configuration:

|Parameter Name | Type | Required | Description|
|:------- |:------ |:--- |:--------|
|Addr | string | Yes | Proxy address|
|User | string | No | User name|
|Passwd | string | No | Password|

`Https ` Structure configuration:

|Parameter Name | Type | Required | Description|
|:-------- |:------ |:--- |:--------|
|Addr | string | Yes | Proxy address|
|User | string | No | User name|
|Passwd | string | No | Password|

`Accounts ` Structure configuration:

|Parameter Name | Type | Required | Description|
|:--- |:---- |:---- |:--------|
|Openurls | []string | No | The URL address accessed when the browser is opened. Please note that currently only one URL can be added|
|GroupID | string | No | The new fingerprint environment created by the group ID is grouped to the specified location|
|User | string | No | The URL environment account that the platform account needs to automatically log in to|
|Passwd | string | No | The password for the platform account to automatically log in to the URL environment password|
|Cookie | string | No | To enable cookies for the environment, both the account and cookie cannot be filled in at the same time. When this field is empty, it means that cookie data will not be stored. If cookies need to be synchronized, this field is required. Please pass "[]" |

`Finger ` Structure configuration:

|Parameter Name | Type | Required | Description|
|:------ |:---- |:----|:------- |
| kernelversion  | string   | No   | kernelversion  Browser kernel major version number (default 107, can be 107, 119, 122) |
|UaVersion | int | No | Browser large version number currently supports automatic generation without transmitting 100-117|
|System | string | No | Currently supported operating system versions (Windows 7, Windows 8, Windows 8.1, Windows 10, Windows 11, iOS 14, iOS 15, iOS 16, Android 9, Android 10, Android 11, Android 12, Android 13, MacOS 10, MacOS 11, MacOS 12, MacOS 13) do not transmit and will automatically generate All Windows. "All Windows": is automatically generated in all supported Windows operating systems; "All IOS": generated in all supported IOS systems; All Android: Randomly across all Android systems All MacOS: Randomly across all MacOS|
|UserAgent | string | No | UserAgent does not write and is automatically generated based on the system and browser version|
|Language | [] string | No | The language of the browser will not be transmitted. It will automatically generate a detailed list of supported languages based on the proxy IP address (if using dynamic IP, it will be automatically generated into Chinese)|
|Zone | string | No | Time zone not transmitted will automatically generate a detailed list of supported time zones based on the proxy IP address (if using dynamic IP to automatically generate Beijing time)|
|DPI | string | No | Automatic generation of plane resolution empty|
|FontList | [] string | No | The font list is not transmitted and is automatically generated by the system|
|WebRTC | int | No | Chrome instant messaging component, supports: 3 privacy; 2 replacement, using proxy IP to cover the real IP, using proxy scenarios; 1. Real, the website will obtain the real IP address; 4 Disabled (default), website will not be able to obtain IP address|
|WebRTCIP | string | no | internal network IP; Configure when WebRTC is set to 2|
|Canvas | int | No | Browser Canvas Fingerprint Switch 1 Invisibility 2 Tendency Random 3 Tendency Consistent Recognition|
|WebGl | int | No | Browser webgl metadata fingerprint switch 1 Invisible 2 Real (default)|
|AudioContext | int | No | 1 Invisible 2 Real|
|SpeedVoices | int | No | SpeedVoices fingerprint, 1: Each browser uses the current computer's default SpeedVoices. 2: Add corresponding noise and generate different SpeedVoices for each browser on the same computer (default)|
|MediaDevice | int | No | Media device switch, 1: Off (each browser uses the default media device ID of the current computer) 2: On (use matching values instead of your actual media device ID, noise) (default)|
|Cpu | int | No | CPU core quantity will be automatically generated if not transmitted|
|Mem | float64 | No | Memory parameters will be automatically generated if not passed|
|DeviceName | string | No | Computer name will be automatically generated if not transmitted (up to 15 characters in length)|
|Mac | string | No | MAC address will be automatically generated if not transmitted|
|Hardware | int | No | Hardware acceleration 1 enabled (default) 2 disabled|
|Bluetooth | int | No | Bluetooth 1 on 2 off (default)|
|DoNotTrack | int | no | do not track browser settings 1 do not enable 2 enable 3 default (default)|
|Enabling ScanPort | int | No | Port scanning protection 1 is enabled (default) 2 is disabled|
|ScanPort | [] int | No | Whitelist 0~65535, disable status, do not write. When Enabling ScanPort is 1, it will automatically generate a local port if it is empty|
|Geographic | object | no | geographic location (default to using IP location dynamic proxy IP not supported)|

`Geometric ` Structure configuration:

|Parameter Name | Type | Required | Description|
|:-- |:-- |:--|:--|
|Enable | int | no | enable 1 (default) ask 2 prohibit 3|
|Useip | int | no | 1. Use IP location (default), 2. Use custom|
|Longitude | string | No | Longitude is used when enable equals 1 or 2 and UseIP equals 0|
|Latitude | string | No | Latitude|
|Accuracy | string | no | accuracy (in meters)|

Example

```js
const requestBody = {
  browser: [
    {
      name: "Fingerprint browser",
      proxy: {
        uuid: "",
        public_ip: "",
        type: "https",
        https: {
          Addr: "",
        },
      },
      accounts: {
        openurls: ["www.baidu.com"],
        groupid: "",
        cookie: "",
        passwd: "123456",
        user: "zhanghao",
      },
      finger: {
        UAversion: 117,
        System: "Android 12",
        UserAgent: "Mozilla/5.0 (Linux; Android 12; V2165A Build/SP1A.210812.003; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/107.0.5304.141 Mobile Safari/537.36 XWEB/5169 MMWEBSDK/20230604 MMWEBID/8106 MicroMessenger/8.0.38.2400(0x28002658) WeChat/arm64 Weixin NetType/WIFI Language/zh_CN ABI/arm64",
        Language: [],
        Zone: "",
        DPI: "随机",
        FontList: [],
        WebRTCIP: "",
        Canvas: 2,
        WebGl: 1,
        WebGLVendor: "Google Inc. (NVIDIA)",
        AudioContext: 1,
        SpeechVoices: 1,
        MediaDevice: 1,
        Cpu: 8,
        Mem: 2,
        DeviceName: "",
        Mac: "",
        Hardware: 1,
        Bluetooth: 1,
        DoNotTrack: 1,
        EnableScanPort: 1,
        ScanPort: [155],
        geographic: {
          enable: 1,
          useip: 1,
        },
      },
    },
  ],
};
```

Return data

```json
{
  "code": 0,
  "msg": "Success",
  "data": {
    "browse": [{ "id": "1b9f203c9d989a602e52fe1e1eb65025", "name": "Fingerprint browser" }]
  }
}
```
|Parameter Name | Type | Description|
|:-------- |:-------- | --------|
|Code | int | Execution status code 0 successful -1 Input format error -2 Quantity acquisition exception -4 Account login exception|
|Msg | string | Returns success or failure message|
|Name | string | Window name interface passed from you|
|ID | string | New fingerprint window ID|
