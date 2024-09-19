### Basic information

> GET /api/v2/browser/stop

Interface Description: Used to close the browser corresponding to the account, and requires specifying the account ID.

### Request parameters
|Parameter Name | Type | Required | Description|
|:---- |:-- |:-- |:-- |
|Account_id | string | Yes | Account ID, a unique ID generated after successful account import|

### Request example

```
http://localhost:50213/api/v2/browser/stop?account_id=d03ca5de08ec8e02c4b78558ee84d7fc
```
### Return data

| Parameter Name | Type | Description |
| :------- | :----- | :---- |
| code     | int    | 0 Success -1 Input Format Error -2 Query Exception -4 Account Login Exception |
| msg      | string | Returns success or failure message                                            |

Execution successful

```json
{
  "Code": 0,
  "Data": {},
  "Msg": "success"
}
```

Execution failed

```json
{
  "Code": -1,
  "Data": {},
  "Msg": "failed"
}
```