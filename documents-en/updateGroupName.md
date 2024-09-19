### Basic information

>POST /api/v2/userapi/group/update

### Request parameters

|Parameter Name | Type | Required | Description|
|:------ |:------ |:--|:--|
|Groupid | string | Yes | GroupID|
|Name | string | No | Group name (2 to 40 characters in length)|

Return data

```json
{
  "Code": 0,
  "Msg": "Success"
}
```
|Parameter Name | Type | Description|
|:------- |:-------- |:--------|
|Code | int | Execution status code 0 successful -1 Input format error -2 Group name too long or too short -4 Account login exception|
|Msg | string | Returns success or failure message|