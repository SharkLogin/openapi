### Basic information

> POST /api/v2/userapi/user/list

### Request parameters

|Parameter Name | Type | Required | Description|
|:-------- |:-------- |:-------- |:--------|
|Browserid | []string | Yes | Browser fingerprint window ID list|

Return data

```json
{
    "code":0,
    "msg":"Success",
    "data":{
        "apibrowser":[
            {
                "Name":"Test Window-1",
                "browserid":"23t87reotgjshgresogjhi49",
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
            },
            {
                "Name":"Test Window-2",
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

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|Code | int | 0 successful -1 input format error -4 account login exception|
|Msg | string | Returns success or failure message|

`Apibrowser ` struct array:

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|Name | string | The name of the fingerprint browser|
|Browserid | string | To modify the ID number of the browser window|
|Proxy | object | proxy information (see 'proxy' structure configuration for details)|
|Accounts | object | Please refer to the 'accounts' structure configuration for details|

`Proxy ` structure configuration:

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|Type | string | Proxy types can be selected: official (purchased on our official website), self (already on our own proxy list), socks5, http, https, local (local)|
|Socks5 | object | socks5 proxy (see 'socks5' structure configuration for details)|

`Socks5 ` Structure configuration:

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|Addr | string | Proxy address|
|User | string | username|
|Passwd | string | Password|

`Accounts ` structure configuration:

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|Openurls | string | Other URL addresses accessed when the browser is opened|
|Groupid | string | GroupID|
|User | string | platform account|
|Passwd | string | Platform password|
|Cookie | string | Account or cookie cannot be filled in simultaneously|

