### Basic information

> POST /api/v2/userapi/user/delete

### Request parameters
|Parameter Name | Type | Required | Description|
|:------ |:------ |:----------|:----------|
|Browserid | []string | Yes | ID of the browser fingerprint window to be deleted|

Return data

```json
{
  "code": 0,
  "msg": "Success",
}
```

|Parameter Name | Type | Description|
|:---- |:----|:----|
|code | int | 0 successful -1 input format error -4 account login exception|
|msg | string | Returns success or failure message|