### 基礎資訊

> POST /api/v2/userapi/group/create

### 請求參數
|參數名稱|類型|必填|說明|
|:-- |:--- |:--- |:---- |
|name|string|是|分組名稱（2到40個字元長度）|

### 請求示例

```
http://localhost:50213/api/v2/userapi/group/create
```
### 請求體

```json
{
    "name": "xxx"
}
```

### 返回數據

|參數名稱|類型|說明|
|:------- |:----- |:------ |
| code | int |執行狀態碼0成功-1輸入格式錯誤-2分組名稱太長或者太短-3這個組名已經創建了-4帳號登入异常|
|msg|string|返回成功或者失敗消息|
|groupid|string|新建的分組ID|
|group|string|新建的分組名|

執行成功

```json
{
	"code":0,
	"msg":"Success",
	"data":{
	"groupid":"fdrgdgsfgsertgreaay34575422",
	"group":"指紋瀏覽器測試分組"
	}
}
```

執行失敗

```json
{
    "code": -1,
    "msg": "fail message",
    "data": {
        "groupid": "",
        "group": ""
    }
}
```