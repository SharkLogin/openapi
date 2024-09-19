### Basic Information

> POST /api/v2/userapi/user/shopseriallist

Return Data

```json
{
    "code": 0,
    "msg": "Success",
    "data": {
        "list": [
            {
                "shopId": "b2a354395c06b5e16e",
                "serial": 96
            },
            {
                "shopId": "ebf96c272b708c944ef1a16",
                "serial": 89
            },
            {
                "shopId": "e7fd6d69588b5de2dffdd3f2",
                "serial": 88
            },
            {
                "shopId": "d4a41c1f5329addd406c5b4",
                "serial": 10
            }
        ]
    }
}
```

| Parameter Name | Type | Description                       |
| :-------- | :------ | :------------------------------------- |
| code     | int    | 0 Success -1 Input Format Error -2 Query Exception -4 Account Login Exception |
| msg      | string | Returns success or failure message |
| shopId      | string | Returned environment ID |
| serial      | int | Returned environment number |

