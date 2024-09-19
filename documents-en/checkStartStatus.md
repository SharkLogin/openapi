### Basic information

> GET /api/v2/browser/status

Interface Description: Used for the startup status of the account browser, which requires specifying the account ID.

### Request parameters

|Parameter Name | Type | Required | Description|
|:------- |:----- |:--- |:------- |
|Account_id | string | Yes | Account ID, a unique ID generated after successful account import|

### Request example

```
http://localhost:50213/api/v2/browser/status?account_id=d03ca5de08ec8e02c4b78558ee84d7fc
```

### Return data

|Parameter Name | Type | Description|
|:------- |:----- |:--- |
|Status | string | Browser opened and running "Active", if not opened, it is "Inctive"|
|Selenium | string | browser debug interface, can be used for selenium automation|
|Puppeter | string | Browser debug interface, can be used for Puppeter automation|



Execution successful
```json
{
  "Code": 0,
  "Data":{
    "Status": "Active",
    "Ws":{
      "Selenium": "127.0.0.1:xxxx",
      "Puppeter": "ws://127.0.0.1: xxxx/devtools/browser/xxxxxx"
    }
  }
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