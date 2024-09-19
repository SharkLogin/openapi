### Basic information

> POST /api/v2/userapi/user/reggroup

### Request parameters

|Parameter Name | Type | Required | Description|
|:------ |:------ |:----------|:----------|
|Browserid | []string | Yes | ID of the browser fingerprint window to be replaced|
|Groupid | string | Yes | The replaced group ID|

Return data

```json
{
  "Code": 0,
  "Msg": "Success",
}
```

|Parameter Name | Type | Description|
|:------ |:------|:------|
|Code | int | 0 successful -1 input format error -4 account login exception|
|Msg | string | Returns success or failure message|