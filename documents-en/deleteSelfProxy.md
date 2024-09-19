### Basic information

> POST/API/v2/userapi/selfproxy/delete

### Request parameters

|Parameter Name | Type | Required | Description|
|:------ |:---- |:---- |:----|
|deviceid | array | yes | proxy id|

Example
```json
const requestBody = {
  "deviceid":[
    "9a8cc12c5e1663e3efcb05e6608869dc"
  ]
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
|:------ |:------ |:-----|
|Code | int | 0 Success -1 Input Format Error -2 Service Exception -4 Account Login Exception|
|Msg | string | Returns success or failure message|