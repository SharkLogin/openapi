### 基礎資訊

> POST /api/v2/userapi/user/shopdetaillist

### 請求參數

| 參數名稱 | 類型   | 必填 | 說明               |
| :--------- | :-------- | :---- | :-------------------- |
| browserid | []string | 是   | 瀏覽器指紋視窗ID |

### 請求示例

```
http://localhost:50213/api/v2/userapi/user/shopdetaillist
```
### 請求體

```json
{
    "browserid": [
        "d03ca5de08ec8e02c4b78558ee84d7fc",
        "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    ]
}
```

### 返回數據

| 參數名稱 | 類型 | 說明                                |
| :-------- | :------ | :------------------------------------- |
| code     | int    | 0成功-1輸入格式錯誤-2服務异常-4帳號登入异常 |
| msg      | string | 返回成功或者失敗消息        |

`browser` 結構體數組：

| 參數名稱 | 類型 | 說明                            |
| :--------- | :------ | :--------------------------------- |
| name      | string | 指纹浏览器的名称          |
| browserid | string | 要修改流覽器窗口的ID號 |
| notes      | string | 備註                |
| is_star_tag      | int | 是否星標  1星標0未星標    |
| serial      | int | 序號               |
| cookie      | string |  cookie json字符串                 |
| group      | object | 分組  詳見`group`結構體配寘 |
| label      | object | 標籤  詳見`label`結構體配寘 |
| proxy     | object | 代理資訊（詳見`proxy`結構體配寘） |
| accounts  | object | 詳見`accounts`結構體配寘 |
| fingerprint  | object | 詳見`fingerprint`結構體配寘 |

`group`結構體配寘：

| 參數名稱 | 類型 | 說明   |
| :-------- | :------ | :-------- |
| name     | string | 分組名 |
| groupid     | string | 分組id  |

`label`結構體配寘：

| 參數名稱 | 類型 | 說明   |
| :-------- | :------ | :-------- |
| name     | string | 標籤名 |
| id     | string | 標籤id |

`proxy`結構體配寘：

| 參數名稱 | 類型 | 說明                                                       |
| :-------- | :------ | :------------------------------------------------------------ |
| inlie     | string | 代理類型可選official（在我們官網購買的）、self（已經在自有代理清單的）、socks5、http、https、local（本地） |
| socks5   | object | socks5代理（詳見`socks5`結構體配寘） |

`socks5`結構體配寘：

| 參數名稱 | 類型 | 說明   |
| :-------- | :------ | :-------- |
| Addr     | string | 代理地址 |
| User     | string | 用戶名 |
| Passwd   | string | 密碼 |

`http` ：

| 參數名稱 | 類型 |  說明   |
| :------- | :----- |  :------- |
| Addr     | string |  代理地址 |
| User     | string | 用戶名 |
| Passwd   | string |  密碼 |

`https` 結構體配寘：

| 參數名稱 | 類型 | 說明   |
| :------- | :----- |  :------- |
| Addr     | string |  代理地址 |
| User     | string | 用戶名 |
| Passwd   | string |  密碼   |

`accounts`結構體配寘：

| 參數名稱 | 類型 | 說明                        |
| :-------- | :------ | :----------------------------- |
| url | []string | 瀏覽器打開時訪問的其他url地址 |
| name  | string | 網址或者名稱                 |
| user     | string | 平臺帳號                  |
| passwd   | string | 平臺密碼                 |
| lock   | int | 鎖定帳號    1鎖定0不鎖定 |
| enableself   | int | 是否是用戶自定義平臺   0平臺提供的1用戶自定義的 |
| loginurl   | string | 平臺提供的網站訪問地址 |

`finger `結構體配寘：

| 參數名稱   | 類型   |  說明                                                                                                                                            |
| :------------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------------ |
| kernel   | string | 瀏覽器資訊  現在都是Chrome |
| kernelversion   | string | 瀏覽器內核版本  |
| UAversion      | int      |  瀏覽器版本號                                                                                                |
| system         | string   | 作業系統版本 |
| ua      | string   |  UserAgent 訊息                                                                                            |
| language       | []string |  瀏覽器的語言                                    |
| zone           | string   |  時區                                               |
| geographic     | object   |  地理位置（詳見`geographic`結構體配寘）                                                        |
| dpi            | string   |  屏幕分辯率                                                                                                                        |
| fontfinger       | []string | 字體清單                                                                                                                |
| WebRTC         | int      | Chrome即時通信組件，支持：3隱私； 2替換，使用代理IP覆蓋真實IP，代理場景使用； 1真實，網站會獲取真實IP； 4禁用（默認），網站會拿不到IP |
| WebRTCIP       | string   | 內網ip； WebRTC設定為2時配寘 |
| Canvas         | int      |  瀏覽器canvas指紋開關 1關閉 0傾向一致性 2傾向隨機性  |
| WebGl          | int      | 瀏覽器webgl中繼資料指紋開關  1隱身2真實（默認） |
| WebGlInfo          | int      | 根據WebGl生成  2自定義1真實0關閉3自動生成 |
| WebGLVendor          | string      |  根據WebGl生成     |
| WebGLRenderer          | string      |  根據WebGl生成               |
| AudioContext   | int      |  1隱身2真實                                                                                                                            |
| SpeechVoices   | int      | SpeechVoices指紋，1：每個瀏覽器使用當前電腦默認的SpeechVoices 2：添加相應的譟音，同一電腦上為每個瀏覽器生成不同的SpeechVoices（默認） |
| mediadevice    | int      | 媒體設備開關，1：關閉（每個瀏覽器使用當前電腦默認的媒體設備id）2：啟用（使用相匹配的值代替您真實的媒體設備ID，雜訊）（默認） |
| cpu            | int      |  CPU核心數量                                                                                                           |
| mem            | int  |  記憶體參數                                                                                                                      |
| devicename     | string   |  電腦名                                                                                                  |
| mac            | string   |  MAC 地址                                                                                                                      |
| hardware       | int      |  硬體加速1開啟（默認）2關閉                                                                                                     |
| Bluetooth      | int      |  藍牙 1開啟  2關閉（默認）                                                                                                        |
| Donottrack     | int      |  請勿跟踪"瀏覽器設定1不啟用2啟用3默認（默認）                                                                   |
| battery | int      |  電池 1真實  0禁止                                                                                                     |
| enablescanport | int      |  埠掃描防護   1開啟（默認）2關閉                                                                                              |
| scanport       | string    |  白名單0~65535關閉狀態不寫當EnableScanPort是1本地埠                               |
| enableCookie       | int    | 1按環境，0按用戶                                                       |
| enableopen       | int    |  多開設定  1開啟，0關閉                                                      |
| enablenotice       | int    |  網頁通知  1開啟，0關閉                                                    |
| enablepic       | int    |  禁止加載圖片  1開啟，0關閉                                                    |
| picsize       | string  |  圖片大小                                                             |
| Enablesound       | int   | 禁止播放聲音  1開啟，0關閉                                                   |
| Enablevideo       | int    |  禁止加載視頻  1開啟，0關閉                                                   |

`geographic` 結構體配寘：

| 參數名稱 | 類型  |  說明                               |
| :-------- | :------ |  :----------------------------------- |
| enable    | int     | 啟用1（默認）詢問2禁止3 |
| useip     | int     | 1使用ip定位（默認），2使用自定義 |
| longitude | string  | 經度當enable等於1或者2且UseIP等於0時使用 |
| latitude  | string  |  纬緯度                               |
| accuracy  | string  |  精度（米）                           |

執行成功

```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "browser": [
            {
                "browserid": "608b78e0c121e262712eaeaba1aa98e1",
                "name": "指紋瀏覽器_3",
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

執行失敗

```json
{
    "code": -1,
    "msg": "fail message",
    "data": {
        "browser": null
    }
}
```