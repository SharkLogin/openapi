### 基礎資訊
> POST /api/v2/userapi/user/create

### 請求參數

`browser`結構體數組，要配寘的參數資訊（詳見：browser）
`browser`結構體數組，格式如下：

|參數名稱|類型|必填|說明|
|:------- |:----- |:--- |:--------------------------------- |
| name | string |是|瀏覽器名稱|
| proxy | object |xxxxxxxxxx {  "code"：-1，  "data"：{}，  "msg"："failed"}json|代理資訊（詳見`proxy`配寘）|
| accounts | object |否|帳號相關資訊（詳見`accounts`配寘）|
| finger | object |否|瀏覽器指紋資訊（詳見`finger`配寘）|

`proxy`結構體配寘：

|參數名稱|類型|必填|說明|
|:-------- |:----- |:--- |:------------ |
| type | string |是|代理類有以下選項：official（平臺代理清單的）、self（自有代理清單的）、socks5（現在添加的）、http（現在添加的）、https（現在添加的）、local（本地）|
| uuid | string |否|代理ID號當type是official或者是self的時候填寫這選項標識代理的唯一標識可以從UI介面的平臺代理盒自由代理中查看|
| public_ip | string |否|你的代理公網出口IP用於定位使用的IP，如果為空會無法進行IP定位擇優配寘瀏覽器指紋資訊|
| socks5 | object |否|代理資訊當type設定為socks5時設定這個選項（詳見`socks5`配寘）|
| http | object |否|代理資訊當type設定為http時設定這個選項（詳見`http`配寘）|
| https | object |否|代理資訊當type設定為https時設定這個選項（詳見`https`配寘）|
| product | int |否|代理資訊當type設定為official時設定這個選項|

`socks5`結構體配寘：

|參數名稱|類型|必填|說明|
|:------- |:----- |:--- |:------- |
| Addr | string |是|代理地址|
| User | string |否|用戶名 |
| Passwd | string |否|密碼|

`http`結構體配寘：

|參數名稱|類型|必填|說明|
|:------- |:----- |:--- |:------- |
| Addr | string |是|代理地址|
| User | string |否|用戶名 |
| Passwd | string |否|密碼|

`https`結構體配寘：

|參數名稱|類型|必填|說明|
|:------- |:----- |:--- |:------- |
| Addr | string |是|代理地址|
| User | string |否|用戶名 |
| Passwd | string |否|密碼|

`accounts `結構體配寘：

|參數名稱|類型|必填|說明|
|:------- |:------- |:--- |:-------------- |
| openurls | []string |否|瀏覽器打開時訪問的url地址注意現時只支持添加1個|
| groupid | string |否|分組ID創建的新指紋環境分組到指定的位置|
| user | string |否|平臺帳號要自動登錄的url環境帳號|
| passwd | string |否|平臺帳號的密碼要自動登錄的url環境密碼|
| cookie | string |否| 要打開環境的cookie，帳號和cookie不能同時填寫，此欄位值為空時表示不存儲cookie數據，如果需要同步cookie，此欄位必填，請傳“[]” |

`finger `結構體配寘：
|參數名稱|類型|必填|說明|
|:------------- |:------- |:--- |:----- |
| kernelversion  | string   | 否   | kernelversion 瀏覽器內核大版本號（不傳默認107, 可傳107, 119, 122）  |
| UaVersion | int |否|瀏覽器大版本號現時支持100-117不傳自動生成|
| System | string |否|作業系統版本現時支持（Windows 7、Windows 8、Windows 8.1、Windows 10、Windows 11、IOS 14、IOS 15、IOS 16、Android 9、Android 10、Android 11、Android 12、Android 13、MacOS 10、MacOS 11、MacOS 12、MacOS 13）不傳會自動生成All Windows，"All Windows"：是在所有支持的Windows作業系統中自動生成； "All IOS"：在所有支持的IOS系統中生成； "All Android"：在所有Android系統中隨機All MacOS:在所有MacOS中隨機。|
| UserAgent | string |否| UserAgent不寫根據系統和流覽器版本自動生成|
| Language | []string |否|瀏覽器的語言不傳會根據代理IP地址自動生成詳細看支持的語言詳細清單（如果是使用動態IP自動生成為中文）|
| Zone | string |否|時區不傳會根據代理IP地址自動生成詳細查看時區支持的清單（如果是使用動態IP自動生成為北京时間）|
| DPI | string |否|平面分辯率空自動生成|
| FontList | []string |否|字體清單不傳系統自動生成|
| WebRTC | int |否| Chrome即時通信組件，支持：3隱私； 2替換，使用代理IP覆蓋真實IP，代理場景使用； 1真實，網站會獲取真實IP； 4禁用（默認），網站會拿不到IP |
| WebRTCIP | string |否|內網ip； WebRTC設定為2時配寘|
| Canvas | int |否| 瀏覽器canvas指紋開關 1關閉 0傾向一致性 2傾向隨機性 |
| WebGl | int |否|瀏覽器webgl中繼資料指紋開關1隱身2真實（默認）|
| AudioContext | int |否| 1隱身2真實|
| SpeechVoices | int |否| SpeechVoices指紋，1：每個瀏覽器使用當前電腦默認的SpeechVoices 2：添加相應的譟音，同一電腦上為每個瀏覽器生成不同的SpeechVoices（默認）|
| MediaDevice | int |否|媒體設備開關，1：關閉（每個瀏覽器使用當前電腦默認的媒體設備id）2：啟用（使用相匹配的值代替您真實的媒體設備ID，雜訊）（默認）|
| Cpu | int |否| CPU核心數量不傳會自動生成|
| Mem | float64 |否|記憶體參數不傳會自動生成|
| DeviceName | string |否|電腦名不傳會自動生成（15個字元長度以內）|
| Mac | string |否| MAC地址不傳會自動生成|
| Hardware | int |否|硬體加速1開啟（默認）2關閉|
| Bluetooth | int |否|藍牙1開啟2關閉（默認）|
| DoNotTrack | int |否|請勿跟踪"瀏覽器設定1不啟用2啟用3默認（默認）|
| EnableScanPort | int |否|埠掃描防護1開啟（默認）2關閉|
| ScanPort | []int |否|白名單0~65535關閉狀態不寫當EnableScanPort是1時這裡為空會自動生成本地埠|
| geographic | object |否|地理位置（默認使用IP定位動態代理IP不支持次選項為禁止）|

`geographic`結構體配寘：

|參數名稱|類型|必填|說明|
|:-------- |:------ |:--- |:----------------------------------- |
| enable | int |否|啟用1（默認）詢問2禁止3 |
| useip | int |否| 1使用ip定位（默認），2使用自定義|
| longitude | string |否|經度當enable等於1或者2且UseIP等於0時使用|
| latitude | string |否|緯度|
| accuracy | string |否|精度（米）|


### 請求示例
```
http://localhost:50213/api/v2/userapi/user/create
```

### 請求體

```json
{
  "browser": [
    {
      "name": "指紋瀏覽器",
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
        "System": "Android 12",
        "UserAgent": "Mozilla/5.0 (Linux; Android 12; V2165A Build/SP1A.210812.003; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/107.0.5304.141 Mobile Safari/537.36 XWEB/5169 MMWEBSDK/20230604 MMWEBID/8106 MicroMessenger/8.0.38.2400(0x28002658) WeChat/arm64 Weixin NetType/WIFI Language/zh_CN ABI/arm64",
        "Language": [],
        "Zone": "",
        "DPI": "隨機",
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


### 返回數據

|參數名稱|類型|說明|
|:------- |:----- |:------------------------- |
| code | int |執行狀態碼0成功-1輸入格式錯誤-2獲取數量异常-4帳號登入异常|
| msg | string |返回成功或者失敗消息|
| name | string |視窗名稱介面自你傳的|
| id | string |新的指紋視窗id |


執行成功

```json
{
  "code": 0,
  "msg": "Success",
  "data": {
    "browse": [{ "id": "1b9f203c9d989a602e52fe1e1eb65025", "name": "指紋瀏覽器" }]
  }
}
```

執行失敗
```json
{
    "code": -1,
    "msg": "fail message",
    "data": {
        "browse": null
    }
}
```