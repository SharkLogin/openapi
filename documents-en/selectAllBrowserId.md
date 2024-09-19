### Basic information
> POST /api/v2/userapi/user/showrist

Return data
```json
{
  "Code": 0,
  "Msg": "Success",
  "Data":{
    "ShopIds":[
      "Bfd0b654a605f9d53e5a5cdac939d74",
      "Fbd2bc962b08518cb6be1acb8ef00",
      "B0d6326c9f05c91dccb72e59f083",
      "0d5fcf6d3df35b2bbfcdd5abd8b9",
      "24b6eed92e3a88e8d7f5a71ab0dc",
      "A75e5c7346650f4baa1cc8176e613",
      "A3c9a8923268f77637ef2cbd4a1e7"
      ]
    }
  }
```

|Parameter Name | Type | Description|
|:------ |:----------|:----------|
|Code | int | 0 Success -1 Input Format Error -2 Query Exception -4 Account Login Exception|
|Msg | string | Returns success or failure message|
|ShopIds | []string | The ID of the returned environment list|