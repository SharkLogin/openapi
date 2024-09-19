### Basic information

> POST/API/v2/userapi/selfproxy/list

### Request parameters

|Parameter Name | Type | Required | Description|
|:------ |:---- |:---- |:-----|
|Page | int | Yes | Page number|
|PageSize | int | Yes | Page size per page|
|Name | string | no | proxy name|

Example
```json
Const requestBody = {
  "Page": 1,
  "PageSize": 10,
  "Name": "
};
````

Return data
```json
{
  "Code": 0,
  "Msg": "Success",
  "Data":{
  "List":[
    {
      "Deviceid": "cc12c5e1663e3efcb05e66088XX",
      "Companyid": "e9b455594c05b52210226XX",
      "Name": "Proxy modification",
      "Proxyaddr": "1.1.1.1:2333",
      "Proxytype": 1,
      "User": "99999",
      "Passwd": "55555",
      "Notes": "Modification 1",
      "Createdat": "2024-04-12 15:58:06"
    }
  ],
  "Total": 1,
  "PageSize": 10,
  "CurrentPage": 1
  }
}
```

|Parameter Name | Type | Description|
|:----- |:------ |:---|
|Code | int | 0 Success -1 Input Format Error -2 Service Exception -4 Account Login Exception|
|Msg | string | Returns success or failure message|
|Deviceid | string | proxy id|
|Companyid | string | team ID|
|Name | string | Agent name|
|Proxytype | int | proxy type   1: with username and password sock5 protocol   3: without username and password socks5 protocol   4: http protocol   5: https protocol   6: with username and password protocol   7: https with username and password protocol |
|Proxyaddr | string | proxy address|
|User | string | Login account|
|Passwd | string | Login password|
|Notes | string | notes|
|Createdat | string | Creation time|

