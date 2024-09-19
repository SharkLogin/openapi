### 基礎資訊
> POST /api/v2/userapi/user/list

### 請求參數

|參數名稱|類型|必填|說明|
|:--------- |:-------- |:---- |:------------------ |
| browserid | []string |是|瀏覽器指紋視窗ID清單|

### 請求示例

```
http://localhost:50213/api/v2/userapi/user/list
```

### 請求體

```json
{
    "browserid":[
        "08638991e03d59ccb9d26571bae80427",
        "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    ]
}
```

### 返回數據
|參數名稱|類型|說明|
|:-------- |:------ |:------------------------------- |
| code | int | 0成功-1輸入格式錯誤-4帳號登入异常|
| msg | string |返回成功或者失敗消息|

`apibrowser`結構體數組：

|參數名稱|類型|說明|
|:--------- |:------ |:--------------------------------- |
| Name | string |指紋瀏覽器的名稱|
| browserid | string |要修改流覽器窗口的ID號|
| proxy | object |代理資訊（詳見`proxy`結構體配寘）|
| accounts | object |詳見`accounts`結構體配寘|

`proxy`結構體配寘：
|參數名稱|類型|說明|
|:-------- |:------ |:-------------------- |
| type | string |代理類型可選official（在我們官網購買的）、self（已經在自有代理清單的）、socks5、http、https、local（本地）|
| socks5 | object | socks5代理（詳見`socks5`結構體配寘）|
| public_ip | string | ip地址 |
| uuid | string | 代理設備id |
| socks5   | object | socks5代理（詳見`socks5`結構體配寘） |
| http | object | http代理（詳見`http`結構體配寘） |
| https | object | https代理（詳見`https`結構體配寘） |
| zhima | object | zhima代理（詳見`zhima`結構體配寘） |

`socks5`結構體配寘：

|參數名稱|類型|說明|
|:-------- |:------ |:-------- |
| Addr | string |代理地址|
| User | string |用戶名|
| Passwd | string |密碼|

`http`結構體配寘：

|參數名稱|類型|說明|
|:-------- |:------ |:-------- |
| Addr | string |代理地址|
| User | string |用戶名|
| Passwd | string |密碼|

`https`結構體配寘：

|參數名稱|類型|說明|
|:-------- |:------ |:-------- |
| Addr | string |代理地址|
| User | string |用戶名|
| Passwd | string |密碼|

`zhima`結構體配寘：

|參數名稱|類型|說明|
| :-------- | :------ | :-------- |
| Url      | string | 提取地址 |
| Interval | number |  提取間隔  |

`accounts`結構體配寘：

|參數名稱|類型|說明|
|:-------- |:------ |:------------------ |
| openurls | string |瀏覽器打開時訪問的其他url地址|
| groupid | string |分組ID |
| user | string |平臺帳號|
| passwd | string |平臺密碼|
| cookie | string |帳號或者cookie不能同時填寫|

執行成功

```json
{
    "code":0,
    "msg":"Success",
    "data":{
        "apibrowser":[
            {
                "Name":"測試窗口-1",
                "browserid":"23t87reotgjshgresogjhi49",
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
                "Name":"測試窗口-2",
                "browserid":"23t87reotgjsh3resogjhi49",
                "proxy":{
                    "type":"socks5",
                    "socks5":{
                        "Addr":"89.2.3.1",
                        "User":"admin",
                        "Passwd":"123456"
                    }
                },
                "accounts":{
                    "openurls":"www.baidu.com",
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

執行失敗

```json
{
    "code": -1,
    "msg": "fail message",
    "data": {
        "apibrowser": null
    }
}
```

