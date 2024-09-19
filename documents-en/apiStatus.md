### Basic information
> GET /status

Interface Description: Used to check the availability of API interfaces.

### Request example

```
http://localhost:50213/status
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
  "Msg": "success"
}
```