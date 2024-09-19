### Basic information

> GET /api/v2/browser/start

`Interface Description`: Used to start the browser corresponding to the account, and the account ID needs to be specified. After successful startup, the browser debug interface can be obtained for executing automation of `selenium` and `puppet`
`Selenium` requires the use of a `Webdriver` that matches the corresponding kernel version. After starting the browser, you can obtain the corresponding path to the `Webdriver` in the return value.

### Request parameters
|Parameter Name | Type | Required | Description|
|:---- |:-- |:-- |:-- |
|Account_id | string | Yes | Account ID, a unique ID generated after successful account import|
|Headless | number | No | Whether it is a headless browser. 1: Yes|

### Request example

```
http://localhost:50213/api/v2/browser/start?account_id=d03ca5de08ec8e02c4b78558ee84d7fc
```

### Return data

|Parameter Name | Type | Description|
|:---- |:-- |:--|
|Selenium | string | browser debug interface, can be used for selenium automation|
|Puppeter | string | browser debug interface, can be used for Puppeter automation|
|DebuggingPort | string | debug port|
|Webdriver | string | webdriver path|

Execution successful

```json
{
  "Code": 0,
  "Data":{
    "Ws":{
      "Selenium": "127.0.0.1:xxxx",
      "Puppeter": "ws://127.0.0.1: xxxx/devtools/browser/xxxxxx"
    },
    "DebuggingPort": "xxxx",
    "Webdriver": "C: \ xxxx \ chrome driver. exe"
  },
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