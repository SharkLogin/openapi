### 基礎資訊
> POST /api/v2/userapi/user/delete

### 請求參數

|參數名稱|類型|必填|說明|
|:--------- |:-------- |:---- |:------------------------ |
| browserid | []string |是|要删除的瀏覽器指紋視窗ID |

### 請求示例

```
http://localhost:50213/api/v2/userapi/user/delete
```

### 請求體

```json
{
    "browserid": [
			"d03ca5de08ec8e02c4b78558ee84d7fc",
			"08638991e03d59ccb9d26571bae80427"
		]
}
```

### 返回數據

|參數名稱|類型|說明|
|:-------- |:------ |:------------------------------------- |
| code | int | 0成功-1輸入格式錯誤-4帳號登入异常|
| msg | string |返回成功或者失敗消息|

執行成功

```json
{
	"code":0,
	"msg":"Success",
}
```

執行失敗

```json
{
    "code": -1,
    "msg": "failed"
}
```


