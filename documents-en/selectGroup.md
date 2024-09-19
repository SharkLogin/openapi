### Basic information

> POST /api/v2/userapi/group/list

### Request parameters

|Parameter Name | Type | Required | Description|
|:------ |:------ |:------ |:------|
|Group | string | No | Fuzzy group name|
|Offer | int | Yes | Calculate from the first offer (minimum offer is 0)|
|Number | int | Yes | The number of entries to be extracted (maximum not exceeding 20)|

Return data

```json
{
  "Code": 0,
  "Msg": "Success",
  "Data":{
    "Group":[
      {
        "Name": "Cloud Login Browser Test Group-1",
        "Gropid": "fdrgdgsfgsertgreaay34575422"
      },
      {
        "Name": "Cloud Login Browser Test Group-2",
        "Gropid": "fd2rgdgsfgsert3reaa44575424"
      }
    ]
  }
}
```

|Parameter Name | Type | Description|
|:-------- |:-------- |:--------|
|Code | string | Execution status code 0 successful -1 Input format error -2 Quantity acquisition exception -4 Account login exception|
|Msg | string | Returns success or failure message|
|Name | string | Group name|
|Groupid | string | GroupID|