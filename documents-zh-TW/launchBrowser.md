### 基礎資訊

> GET /api/v2/browser/start

介面描述：用於啟動環境對應的瀏覽器，需要指定環境ID，啟動成功後可以獲取瀏覽器debug介面用於執行`selenium`和`puppeteer`自動化。` Selenium`需要使用到對應內核版本匹配的`Webdriver`。 啟動瀏覽器後可在返回值中拿到對應的`Webdriver`的路徑。

### 請求參數

|參數名稱|類型|必填|說明|
|:----|:--|:--|:---|
| account_id | string |是|環境ID，環境導入成功後生成的唯一ID |
| headless | number |否|是否無頭瀏覽器。 1:是|

### 請求示例

```
http://localhost:50213/api/v2/browser/start?account_id=d03ca5de08ec8e02c4b78558ee84d7fc
```

### 返回數據
| 參數名稱 | 類型   | 說明                                                          |
| :------- | :----- | :----------------------------------------------------------- |
| code     | int    | 執行狀態碼 0成功 -1輸入格式錯誤 -2獲取數量異常 -4帳號登錄異常 -6未實名認證 |
| msg      | string | 返回成功或者失敗消息                                            |

`data`結構體配置
|參數名稱|類型|說明|
|:----|:--|:--|
| ws | object | websocket信息 |
| debuggingPort | string | debug端口 |
| webdriver | string | webdriver路徑 |

`ws`結構體配置
|參數名稱|類型|說明|
|:----|:--|:--|
| selenium | string | 瀏覽器debug接口，可用於selenium自動化 |
| puppeteer | string | 瀏覽器debug接口，可用於puppeteer自動化 |


執行成功
```json
{
	"code":0,
	"data":{
	"ws":{
		"selenium":"127.0.0.1:xxxx",
		"puppeteer":"ws://127.0.0.1:xxxx/devtools/browser/xxxxxx"
	},
	"debuggingPort":"xxxx",
	"webdriver":"C:\xxxx\chromedriver.exe"
	},
	"msg":"success"
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