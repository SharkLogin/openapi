### Basic information

> POST/API/v2/userapi/user/showdetaillist

### Request parameters

|Parameter Name | Type | Required | Description|
|:------- |:------ |:------ |:-----|
|Browserid | [] string | Yes | Browser fingerprint window ID|

Return data

```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "browser": [
            {
                "browserid": "608b78e0c121e262712eaeaba1aa98e1",
                "name": "Fingerprint Browser_1",
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
                    },
                    "v2Ray": {
                        "addr": "",
                        "uuid": ""
                    },
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

|Parameter Name | Type | Description|
|:--- |:----|:---|
|Code | int | 0 successful -1 input format error -2 query error -4 account login exception|
|Msg | string | Returns success or failure message|

`Browser ` Structure array:

|Parameter Name | Type | Description|
|:------ |:----- |:--------|
|Name | string | The name of the fingerprint browser|
|Browserid | string | To modify the ID number of the browser window|
|Notes | string | notes|
|Is_star_tag | int | Is star 1 star 0 not star marked|
|Serial | int | serial number|
|Cookie | string | Cookie JSON string|
|Group | object | For more information on grouping, please refer to the 'group' structure configuration|
|Label | object | For more information on labels, please refer to the 'label' structure configuration|
|Proxy | object | proxy information (see 'proxy' structure configuration for details)|
|Accounts | object | Please refer to the 'accounts' structure configuration for details|
|Fingerprint | object | Please refer to the 'fingerprint' structure configuration for details|

`Group` structure configuration:

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|Name | string | Group name|
|Groupid | string | groupid|

`Label ` Structure configuration:

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|Name | string | tag name|
|ID | string | tag ID|

`Proxy ` structure configuration:

|Parameter Name | Type | Description|
|:------ |:--- |:---|
|Inlie | string | Optional proxy types: official (purchased on our official website), self (already on our own proxy list), socks5, http, https, local (local)|
|Socks5 | object | socks5 proxy (see 'socks5' structure configuration for details)|

`Socks5 ` Structure configuration:

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|Addr | string | Proxy address|
|User | string | username|
|Passwd | string | Password|

`HTTP` structure configuration:

|Parameter Name | Type | Description|
|:------- |:-------- |:--------|
|Addr | string | Proxy address|
|User | string | username|
|Passwd | string | Password|

`Https ` Structure configuration:

|Parameter Name | Type | Description|
|:------- |:------- |:--------|
|Addr | string | Proxy address|
|User | string | username|
|Passwd | string | Password|

`Accounts` structure configuration:

|Parameter Name | Type | Description|
|:----- |:------|:------|
|URL | [] string | Other URL addresses accessed when the browser is opened|
|Name | string | URL or name|
|User | string | platform account|
|Passwd | string | Platform password|
|Lock | int | Lock account 1 Lock 0 Do not lock|
|Enableself | int | Is it a user-defined platform 0 provided by platform 1 user-defined|
|LoginURL | string | The website access address provided by the platform|

`Finger` Structure configuration:

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|The kernel | string | browser information is now in Chrome|
|Kernel version | string | browser kernel version|
|UAversion | int | Browser ID|
|System | string | Operating system version|
|Ua | string | UserAgent information|
|Language | [] string | The language of the browser|
|Zone | string | time zone|
|Geographic | object | geographic location (see 'geographic' structure configuration for details)|
|Dpi | string | plane resolution |
|Fontfinger | [] string | List of fonts|
|WebRTC | int | Chrome instant messaging component, supports: 3 privacy; 2 replacement, using proxy IP to cover the real IP, using proxy scenarios; 1. Real, the website will obtain the real IP address; 4 Disabled (default), website will not be able to obtain IP address|
|WebRTCIP | string | intranet IP; Configure when WebRTC is set to 2|
|Canvas | int | Browser Canvas Fingerprint Switch 1 Invisibility 2 Tendency Random 3 Tendency Consistent Recognition|
|WebGl | int | browser webgl metadata fingerprint switch 1 stealth 2 real (default)|
|WebGlInfo | int | Generate based on WebGl 2 Custom 1 Real 0 Close 3 Auto Generate|
|WebGLVendor | string | Generate based on WebGl|
|WebGLRenderer | string | Generate based on WebGl|
|AudioContext | int | 1 Invisible 2 Realistic|
|SpeedVoices | int | SpeedVoices fingerprint, 1: Each browser uses the current computer's default SpeedVoices. 2: Add corresponding noise and generate different SpeedVoices for each browser on the same computer (default)|
|Mediadevice | int | Media device switch, 1: Off (each browser uses the current computer's default media device ID) 2: On (uses matching values to replace your actual media device ID, noise) (default)|
|CPU | int | Number of CPU cores|
|Mem | int | Memory parameters|
|Devicename | string | Computer name|
|MAC | string | MAC address|
|Hardware | int | Hardware acceleration 1 enabled (default) 2 disabled|
|Bluetooth | int | Bluetooth 1 on 2 off (default)|
|Donottrack | int | Do not track browser settings 1, disable 2, enable 3, default (default)|
|Battery | int | Battery 1 True 0 Prohibited|
|Enablescanport | int | Port scanning protection 1 enabled (default) 2 disabled|
|Scanport | string | whitelist 0~65535, disable status not written when enableScanPort is 1 local port|
|EnableCookie | int | Cookie 1 Security Environment, 0 By User|
|Enableopen | int | Multi open setting 1 on, 0 off|
|Enablenotice | int | Web notification 1 enabled, 0 disabled|
|Enablepic | int | Prohibit loading images 1 on, 0 off|
|Picsize | string | Image size|
|Enabling sound | int | Prohibit playback of sound 1 on, 0 off|
|Enabling video | int | Prohibit loading videos 1 on, 0 off|

`Geometric` Structure configuration:

|Parameter Name | Type | Description|
|:----- |:------|:-----|
|Enable | int | enable 1 (default) query 2 prohibit 3|
|Useip | int | 1 Use IP location (default), 2 Use custom|
|Longitude | string | Longitude used when enable equals 1 or 2 and UseIP equals 0|
|Latitude | string | Latitude|
|Accuracy | string | Precision (in meters)|                     |
