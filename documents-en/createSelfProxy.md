### Basic information

> POST/API/v2/userapi/selfproxy/create

### Request parameters
`Proxy ` structure array, parameter information to be configured (see proxy for details)
`Proxy ` structure configuration:

|Parameter Name | Type | Required | Description|
|:------ |:---- |:---- |:-----|
|Name | string | Yes | Proxy name|
|Proxytype | int | yes | proxy type   1: with username and password sock5 protocol  3: without username and password socks5 protocol   4: http protocol   5: https protocol   6: with username and password protocol   7: https with username and password protocol |
|Proxyaddr | string | Yes | Proxy address|
|Proxyu | string | no | login account|
|Proxyp | string | no | login password|
|Notes | string | no | notes|

Example
```json
Const requestBody = {
  "Proxy":{
    "Name": "Agent 1",
    "Proxytype": 1,
    "Proxyaddr": "1.1.1.1:2333",
    "Proxyp": "7777777",
    "Proxyu": "88888888",
    "Notes": "Proxy"
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
|Parameter Name | Type | Description     |
| :------- | :----- | :------- |
|Code | int | 0 Success -1 Input Format Error -2 Service Exception -4 Account Login Exception|
|Msg | string | Returns success or failure message|
