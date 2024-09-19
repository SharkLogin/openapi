### Basic information

> POST /api/v2/userapi/group/create

### Request parameters

|Parameter Name | Type | Required | Description|
|:-- |:-- |:-- |:-- |
|Name | string | Yes | Group name (2 to 40 characters in length)|

### Return data

```json
{
  "Code": 0,
  "Msg": "Success",
  "Data":{
    "Groupid": "fdrgdgsfgsertgreaay34575422",
    "Group": "Cloud login browser test group"
  }
}
```
|Parameter Name | Type | Description|
|:------ |:------ |:----|
|code | int | Execution status code 0 successful -1 Input format error -2 Group name too long or too short -3 This group name has already been created -4 Account login exception|
|Msg | string | Returns success or failure message|
|Groupid | string | The newly created group ID|
|Group | string | New group name|