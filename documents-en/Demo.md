## Java

```java
OkHttpClient client = new OkHttpClient().newBuilder()
   .build();
MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\r\n\"proxy\": {\r\n\"name\": \"proxy12\",\r\n\"proxytype\": 1,\r\n\"proxyaddr\": \"1.1.1.1:2333\",\r\n\"proxyp\": \"7777777\",\r\n\"proxyu\": \"8888888\",\r\n\"notes\": \"proxy\"\r\n}\r\n}");
Request request = new Request.Builder()
   .url("http://localhost:50213/api/v2/userapi/selfproxy/create")
   .method("POST", body)
   .addHeader("User-Agent", "Apifox/1.0.0 (https://apifox.com)")
   .addHeader("Content-Type", "application/json")
   .addHeader("Authorization", "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTM1OTM3NDgsImp0aSI6IjZmMDAzODUxYzg5MDQ4NzA5ODUzMmM0YzAzYmJlMTg4IiwiaXNzIjoiMjFmNzcwMzIzNDg2NDFlYzllYzU2MGYyMDQwZjdjYzQifQ.jJZtDBm8ya1SZiZoRIW8AZrNGLEykpn9IH3rjPHKvho")
   .addHeader("Accept", "*/*")
   .addHeader("Host", "localhost:50213")
   .addHeader("Connection", "keep-alive")
   .build();
Response response = client.newCall(request).execute();
```

## Swift

```swift
import Foundation
#if canImport(FoundationNetworking)
import FoundationNetworking
#endif

var semaphore = DispatchSemaphore (value: 0)

let parameters = "{\r\n\"proxy\": {\r\n\"name\": \"proxy12\",\r\n\"proxytype\": 1,\r\n     \"proxyaddr\": \"1.1.1.1:2333\",\r\n\"proxyp\": \"7777777\",\r\n\"proxyu\": \"8888888\",\r\n\"notes\": \"proxy\"\r\n}\r\n}"
let postData = parameters.data(using: .utf8)

var request = URLRequest(url: URL(string: "http://localhost:50213/api/v2/userapi/selfproxy/create")!,timeoutInterval: Double.infinity)
request.addValue("Apifox/1.0.0 (https://apifox.com)", forHTTPHeaderField: "User-Agent")
request.addValue("application/json", forHTTPHeaderField: "Content-Type")
request.addValue("Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTM1OTM3NDgsImp0aSI6IjZmMDAzODUxYzg5MDQ4NzA5ODUzMmM0YzAzYmJlMTg4IiwiaXNzIjoiMjFmNzcwMzIzNDg2NDFlYzllYzU2MGYyMDQwZjdjYzQifQ.jJZtDBm8ya1SZiZoRIW8AZrNGLEykpn9IH3rjPHKvho", forHTTPHeaderField: "Authorization")
request.addValue("*/*", forHTTPHeaderField: "Accept")
request.addValue("localhost:50213", forHTTPHeaderField: "Host")
request.addValue("keep-alive", forHTTPHeaderField: "Connection")

request.httpMethod = "POST"
request.httpBody = postData

let task = URLSession.shared.dataTask(with: request) { data, response, error in 
   guard let data = data else {
      print(String(describing: error))
      semaphore.signal()
      return
   }
   print(String(data: data, encoding: .utf8)!)
   semaphore.signal()
}

task.resume()
semaphore.wait()
```

## Go

```go
package main

import (
   "fmt"
   "strings"
   "net/http"
   "io/ioutil"
)

func main() {

   url := "http://localhost:50213/api/v2/userapi/selfproxy/create"
   method := "POST"

   payload := strings.NewReader(`{"proxy":{"name":"text12","proxytype":1,"proxyaddr":"1.1.1.1:2333","proxyp":"7777777","proxyu":"8888888","notes":"text"}}`)

   client := &http.Client {
   }
   req, err := http.NewRequest(method, url, payload)

   if err != nil {
      fmt.Println(err)
      return
   }
   req.Header.Add("User-Agent", "Apifox/1.0.0 (https://apifox.com)")
   req.Header.Add("Content-Type", "application/json")
   req.Header.Add("Authorization", "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTM1OTM3NDgsImp0aSI6IjZmMDAzODUxYzg5MDQ4NzA5ODUzMmM0YzAzYmJlMTg4IiwiaXNzIjoiMjFmNzcwMzIzNDg2NDFlYzllYzU2MGYyMDQwZjdjYzQifQ.jJZtDBm8ya1SZiZoRIW8AZrNGLEykpn9IH3rjPHKvho")
   req.Header.Add("Accept", "*/*")
   req.Header.Add("Host", "localhost:50213")
   req.Header.Add("Connection", "keep-alive")

   res, err := client.Do(req)
   if err != nil {
      fmt.Println(err)
      return
   }
   defer res.Body.Close()

   body, err := ioutil.ReadAll(res.Body)
   if err != nil {
      fmt.Println(err)
      return
   }
   fmt.Println(string(body))
}
```

## PHP

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
   CURLOPT_URL => 'http://localhost:50213/api/v2/userapi/selfproxy/create',
   CURLOPT_RETURNTRANSFER => true,
   CURLOPT_ENCODING => '',
   CURLOPT_MAXREDIRS => 10,
   CURLOPT_TIMEOUT => 0,
   CURLOPT_FOLLOWLOCATION => true,
   CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
   CURLOPT_CUSTOMREQUEST => 'POST',
   CURLOPT_POSTFIELDS =>'{
    "proxy": {
        "name": "proxy12",
        "proxytype": 1,
        "proxyaddr": "1.1.1.1:2333",
        "proxyp": "7777777",
        "proxyu": "8888888",
        "notes": "proxy"
    }
}',
   CURLOPT_HTTPHEADER => array(
      'User-Agent: Apifox/1.0.0 (https://apifox.com)',
      'Content-Type: application/json',
      'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTM1OTM3NDgsImp0aSI6IjZmMDAzODUxYzg5MDQ4NzA5ODUzMmM0YzAzYmJlMTg4IiwiaXNzIjoiMjFmNzcwMzIzNDg2NDFlYzllYzU2MGYyMDQwZjdjYzQifQ.jJZtDBm8ya1SZiZoRIW8AZrNGLEykpn9IH3rjPHKvho',
      'Accept: */*',
      'Host: localhost:50213',
      'Connection: keep-alive'
   ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

## Python

```python
import http.client
import json

conn = http.client.HTTPSConnection("localhost", 50213)
payload = json.dumps({
   "proxy": {
      "name": "proxy12",
      "proxytype": 1,
      "proxyaddr": "1.1.1.1:2333",
      "proxyp": "7777777",
      "proxyu": "8888888",
      "notes": "proxy"
   }
})
headers = {
   'User-Agent': 'Apifox/1.0.0 (https://apifox.com)',
   'Content-Type': 'application/json',
   'Authorization': 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTM1OTM3NDgsImp0aSI6IjZmMDAzODUxYzg5MDQ4NzA5ODUzMmM0YzAzYmJlMTg4IiwiaXNzIjoiMjFmNzcwMzIzNDg2NDFlYzllYzU2MGYyMDQwZjdjYzQifQ.jJZtDBm8ya1SZiZoRIW8AZrNGLEykpn9IH3rjPHKvho',
   'Accept': '*/*',
   'Host': 'localhost:50213',
   'Connection': 'keep-alive'
}
conn.request("POST", "/api/v2/userapi/selfproxy/create", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

## C

```c
CURL *curl;
CURLcode res;
curl = curl_easy_init();
if(curl) {
   curl_easy_setopt(curl, CURLOPT_CUSTOMREQUEST, "POST");
   curl_easy_setopt(curl, CURLOPT_URL, "http://localhost:50213/api/v2/userapi/selfproxy/create");
   curl_easy_setopt(curl, CURLOPT_FOLLOWLOCATION, 1L);
   curl_easy_setopt(curl, CURLOPT_DEFAULT_PROTOCOL, "https");
   struct curl_slist *headers = NULL;
   headers = curl_slist_append(headers, "User-Agent: Apifox/1.0.0 (https://apifox.com)");
   headers = curl_slist_append(headers, "Content-Type: application/json");
   headers = curl_slist_append(headers, "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTM1OTM3NDgsImp0aSI6IjZmMDAzODUxYzg5MDQ4NzA5ODUzMmM0YzAzYmJlMTg4IiwiaXNzIjoiMjFmNzcwMzIzNDg2NDFlYzllYzU2MGYyMDQwZjdjYzQifQ.jJZtDBm8ya1SZiZoRIW8AZrNGLEykpn9IH3rjPHKvho");
   headers = curl_slist_append(headers, "Accept: */*");
   headers = curl_slist_append(headers, "Host: localhost:50213");
   headers = curl_slist_append(headers, "Connection: keep-alive");
   curl_easy_setopt(curl, CURLOPT_HTTPHEADER, headers);
   const char *data = "{\r\n    \"proxy\": {\r\n        \"name\": \"proxy12\",\r\n        \"proxytype\": 1,\r\n        \"proxyaddr\": \"1.1.1.1:2333\",\r\n        \"proxyp\": \"7777777\",\r\n        \"proxyu\": \"8888888\",\r\n        \"notes\": \"proxy\"\r\n    }\r\n}";
   curl_easy_setopt(curl, CURLOPT_POSTFIELDS, data);
   res = curl_easy_perform(curl);
}
curl_easy_cleanup(curl);
```

## C #

```c#
var client = new RestClient("http://localhost:50213/api/v2/userapi/selfproxy/create");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
client.UserAgent = "Apifox/1.0.0 (https://apifox.com)";
request.AddHeader("Content-Type", "application/json");
request.AddHeader("Authorization", "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTM1OTM3NDgsImp0aSI6IjZmMDAzODUxYzg5MDQ4NzA5ODUzMmM0YzAzYmJlMTg4IiwiaXNzIjoiMjFmNzcwMzIzNDg2NDFlYzllYzU2MGYyMDQwZjdjYzQifQ.jJZtDBm8ya1SZiZoRIW8AZrNGLEykpn9IH3rjPHKvho");
request.AddHeader("Accept", "*/*");
request.AddHeader("Host", "localhost:50213");
request.AddHeader("Connection", "keep-alive");
var body = @"{
" + "\n" +
@"    ""proxy"": {
" + "\n" +
@"        ""name"": ""proxy12"",
" + "\n" +
@"        ""proxytype"": 1,
" + "\n" +
@"        ""proxyaddr"": ""1.1.1.1:2333"",
" + "\n" +
@"        ""proxyp"": ""7777777"",
" + "\n" +
@"        ""proxyu"": ""8888888"",
" + "\n" +
@"        ""notes"": ""proxy""
" + "\n" +
@"    }
" + "\n" +
@"}";
request.AddParameter("application/json", body,  ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

## Objective-C

```objective-c
#import <Foundation/Foundation.h>

dispatch_semaphore_t sema = dispatch_semaphore_create(0);

NSMutableURLRequest *request = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:@"http://localhost:50213/api/v2/userapi/selfproxy/create"]
   cachePolicy:NSURLRequestUseProtocolCachePolicy
   timeoutInterval:10.0];
NSDictionary *headers = @{
   @"User-Agent": @"Apifox/1.0.0 (https://apifox.com)",
   @"Content-Type": @"application/json",
   @"Authorization": @"Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTM1OTM3NDgsImp0aSI6IjZmMDAzODUxYzg5MDQ4NzA5ODUzMmM0YzAzYmJlMTg4IiwiaXNzIjoiMjFmNzcwMzIzNDg2NDFlYzllYzU2MGYyMDQwZjdjYzQifQ.jJZtDBm8ya1SZiZoRIW8AZrNGLEykpn9IH3rjPHKvho",
   @"Accept": @"*/*",
   @"Host": @"localhost:50213",
   @"Connection": @"keep-alive"
};

[request setAllHTTPHeaderFields:headers];
NSData *postData = [[NSData alloc] initWithData:[@"{\r\n    \"proxy\": {\r\n        \"name\": \"proxy12\",\r\n        \"proxytype\": 1,\r\n        \"proxyaddr\": \"1.1.1.1:2333\",\r\n        \"proxyp\": \"7777777\",\r\n        \"proxyu\": \"8888888\",\r\n        \"notes\": \"proxy\"\r\n    }\r\n}" dataUsingEncoding:NSUTF8StringEncoding]];
[request setHTTPBody:postData];

[request setHTTPMethod:@"POST"];

NSURLSession *session = [NSURLSession sharedSession];
NSURLSessionDataTask *dataTask = [session dataTaskWithRequest:request
completionHandler:^(NSData *data, NSURLResponse *response, NSError *error) {
   if (error) {
      NSLog(@"%@", error);
      dispatch_semaphore_signal(sema);
   } else {
      NSHTTPURLResponse *httpResponse = (NSHTTPURLResponse *) response;
      NSError *parseError = nil;
      NSDictionary *responseDictionary = [NSJSONSerialization JSONObjectWithData:data options:0 error:&parseError];
      NSLog(@"%@",responseDictionary);
      dispatch_semaphore_signal(sema);
   }
}];
[dataTask resume];
dispatch_semaphore_wait(sema, DISPATCH_TIME_FOREVER);
```

## Ruby

```ruby
require "uri"
require "json"
require "net/http"

url = URI("http://localhost:50213/api/v2/userapi/selfproxy/create")

http = Net::HTTP.new(url.host, url.port);
request = Net::HTTP::Post.new(url)
request["User-Agent"] = "Apifox/1.0.0 (https://apifox.com)"
request["Content-Type"] = "application/json"
request["Authorization"] = "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MTM1OTM3NDgsImp0aSI6IjZmMDAzODUxYzg5MDQ4NzA5ODUzMmM0YzAzYmJlMTg4IiwiaXNzIjoiMjFmNzcwMzIzNDg2NDFlYzllYzU2MGYyMDQwZjdjYzQifQ.jJZtDBm8ya1SZiZoRIW8AZrNGLEykpn9IH3rjPHKvho"
request["Accept"] = "*/*"
request["Host"] = "localhost:50213"
request["Connection"] = "keep-alive"
request.body = JSON.dump({
   "proxy": {
      "name": "proxy12",
      "proxytype": 1,
      "proxyaddr": "1.1.1.1:2333",
      "proxyp": "7777777",
      "proxyu": "8888888",
      "notes": "proxy"
   }
})

response = http.request(request)
puts response.read_body
```

## js

### node.js

package.json

```json
{
  "name": "js-demo",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "start": "node app.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "axios": "^1.6.8",
    "puppeteer-core": "18.2.1"
  }
}

```

app.js

```js
var puppeteer = require("puppeteer-core");
var axios = require("axios");
var browser;

/**
 * Start RPA operations
 * @param {*} ws  The ws address of Puppeteer
 */
const start = async (ws) => {
   browser = await puppeteer.connect({
      browserWSEndpoint: ws,
   });
   const page = await browser.newPage();
   await page.goto("https://example.com");
   await page.screenshot({ path: "screenshot.png" });
   await browser.close();
};

axios
   .get(
      "http://127.0.1:50213/api/v2/browser/start?account_id=******"
   )
   .then((res) => {
      console.log("res", res.data.data.ws.puppeteer);
      start(res.data.data.ws.puppeteer);
   })
   .catch((err) => {
      console.log(err);
   });
```

run

```base
npm install
npm run start
```

### web

```js
var axios = require('axios');

var config = {
   method: 'get',
   url: 'http://localhost:50213/api/v2/browser/start?account_id=******'
};

axios(config)
.then(function (response) {
   console.log(JSON.stringify(response.data));
})
.catch(function (error) {
   console.log(error);
});

```
