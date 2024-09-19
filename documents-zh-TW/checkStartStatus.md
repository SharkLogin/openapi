### 基礎資訊
> GET /api/v2/browser/status

介面描述:用於環境瀏覽器的啟動狀態，需要指定環境ID。

### 請求參數

|參數名稱|類型|必填|說明|
|:----|:-- |:-- |:--- |
| account_id | string |是|環境ID，環境導入成功後生成的唯一ID |

### 請求示例

```
http://localhost:50213/api/v2/browser/status?account_id=d03ca5de08ec8e02c4b78558ee84d7fc
```

### 返回數據

| 參數名稱 | 類型   | 說明  |
| :------- | :----- | :------- |
| code     | int    | 執行狀態碼 0 成功 -1 輸入格式錯誤 -2 獲取數量異常 -4 帳號登錄異常 |
| msg      | string | 返回成功或者失敗消息  |
| data    | object | 返回成功數據  |

​
`data`結構體配置

|參數名稱|類型|說明|
|:----|:-- |:-- |
|status|string|瀏覽器已打開運行中"Active"，未打開則是"Inactive"|
|selenium|string|瀏覽器debug介面，可用於selenium自動化|
|puppeteer|string|瀏覽器debug介面，可用於puppeteer自動化|

執行成功

```json
{
	"code":0,
	"data":{
	"status":"Active",
	"ws":{
		"selenium":"127.0.0.1:xxxx",
		"puppeteer":"ws://127.0.0.1:xxxx/devtools/browser/xxxxxx"
		}
	}
}
```

執行失敗

```json
{
	"code":-1,
	"data":{},
	"msg":"failed"
}
```