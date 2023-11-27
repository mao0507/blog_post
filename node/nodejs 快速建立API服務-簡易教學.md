---
title: nodejs 快速建立API服務-簡易教學
tags: 
  -  NodeJs
categories: Node
date: 2023/11/28 01:29
update: 2023/11/28 01:29
---



## 安裝 nodejs 

[下載連結](https://nodejs.org/en/download)


## 建立專案

```shell
$ mkdir express-server && cd express-server
$ npm init -y 
$ npm install express
```

## 設定 Web Server

### 建立 app.js 

```javascript
const express = require('express');
const app = express();


// req => request 請求內容
// res => response 回應內容

//GET 請求
app.get('/', function (req, res) {
  console.log('首頁GET 請求');
  res.send(' Hello GET ');
});

//POST 請求
app.post('/', function (req, res) {
  console.log('首頁POST 請求');
  res.send(' Hello POST ');
});

//PUT 請求
app.put('/', function (req, res) {
  console.log('首頁PUT 請求');
  res.send(' Hello PUT ');
});

//DELETE 請求
app.delete('/', function (req, res) {
  console.log('首頁DELETE 請求');
  res.send(' Hello DELETE ');
});

// 監聽 Port
const PORT = 9527;
app.listen(PORT, () => {
  console.log(`server working now on ${PORT}`);
});



```


### 執行 app.js 啟動服務器

```shell
$ node app.js
```


## 測試API 連線

### 使用 postman 

#### 甚麼是postman

Postman 是一個可以模擬 HTTP Request 的工具，其中包含常見的 HTTP 的請求方式，
例如： GET 、POST、PUT、DELETE，
而它的主要功能就是能夠快速的測試你的 API 是否能夠正常的請求資料，
並得到正確的請求結果。除了快速測試的功能以外， Postman 還擁有非常容易使用的介面

#### 下載postman

[下載連結](https://www.postman.com/downloads/)

#### 安裝後並執行postman

1. 在輸入框輸入 `localhost:9527`
2. 模式選擇 `GET`
3. 按下 send
4. 會看到 `Hello GET`
![image](https://i.imgur.com/zpI0svS.png)





## 加入套件

### nodemon

#### nodemon 功能
* 自動重啟應用程式
* 持續偵測你的預設程式
* 默認支持 node＆coffeescript，但是易於運行任何可執行文件（比如python，make等）
* 可以忽略特定文件或目錄
* 觀察指定的目錄資料夾
* 與服務器應用程序或一次運行公用程序和 REPLs 一起使用
* 可在 node 中被存取使用

#### 安裝 

```shell
$ npm install nodemon -g  
```


#### 使用方式

```shell
$ nodemon index.js
```


#### script 設定

可以到 package.json檔案內中，
在`scrip` 這個物件底下新建立一個腳本

```json
 "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
    "start":"nodemon app.js"
  },
```

這樣以後要執行服務的時候就可以直接輸入 
```shell
$ npm run start
```




### dotenv

#### 透過 dotenv 套件來隱藏敏感資訊
node.js 是沒有辦法直接讀取到 .env 檔案的，需要另外安裝套件才能讀取
可以將 sql連線 等敏感資料都寫在 .env 來進行管理 

#### 安裝 

```shell
$ npm install dotenv  
```

#### 使用方法

```javascript    
// env檔案

number=123
```

```javascript
require('dotenv').config();
console.log(process.env.number)

// 輸出結果為: 123
```

### bodyparser

#### 為何要安裝
body-parser是非常常用的一個express中介層(middleware)，
作用是對post請求的請求體進行解析。

#### body-parser主要做了什麼

處理不同類型的請求體：例如text、json、urlencoded等，對應的封包主體的格式不同。
處理不同的編碼：例如utf8、gbk等。
處理不同的壓縮類型：比如gzip、deflare等。
其他邊界、異常的處理。



#### 安裝

```shell
$ npm install body-parser
```


#### 使用方法

使用非常簡單，以下兩行程式碼已經涵蓋了大部分的使用場景。

```javascript
const bodyParser = require('body-parser')
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: false }));
```



## 參考
[express](https://expressjs.com/zh-tw/)
[nodemon](https://andy6804tw.github.io/2017/12/24/nodemon-tutorial/)
[dotenv](https://www.npmjs.com/package/dotenv)
[body-parser](https://www.cnblogs.com/chyingp/p/nodejs-learning-express-body-parser.html)