### Basic information

> POST/API/v2/userapi/selfproxy/update

### Request parameters

`Proxy` structure array, parameter information to be configured (see proxy for details)
`Proxy` structure configuration:

|Parameter Name | Type | Required | Description|
|:------ |:---- |:---- |:---|
|Deviceid | string | yes | proxy id|
|Name | string | No | If the proxy name is empty, it means it will not be modified|
|Proxytype | int | no | proxy type. If 0 is passed, it means it will not be modified. 1: There is a username and password sock. 5 Protocol 3: No username and password sock. 5 Protocol 4: HTTP Protocol 5: HTTPS Protocol 6: HTTP has a username and password protocol 7: https has a username and password protocol|
|Proxyaddr | string | No | If the proxy address is empty, it means it will not be modified|
|Proxyu | string | No | If the login account is empty, it means it will not be modified|
|Proxyp | string | no | If the login password is left blank, it means it will not be changed|
|Notes | string | No | If the note is empty, it means it will not be modified|

Example
```json
Const requestBody = {
  "Proxy":{
    "Name": "Proxy modification",
    "Proxytype": 0,
    "Proxyaddr": "",
    "Deviceid": "XXXX5e1663e3efcb05e66XXXXc",
    "Notes": "modify",
    "Proxyu": "99999",
    "Proxyp": "55555"
  }
};
```
Return data
```json
{
  "Code": 0,
  "Msg": "Success"
}
```

|Parameter Name | Type | Description|
|:------ |:------ |:------|
|Code | int | 0 Success -1 Input Format Error -2 Service Exception -4 Account Login Exception|
|Msg | string | Returns success or failure message|



