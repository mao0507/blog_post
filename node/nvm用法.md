---
title: 安裝NVM教學
tags: - NodeJs
categories: Node
date: 2023/06/05
update: 2023/06/05
---



## 簡介

在工作中常常會需要去接手他人的程式碼，每個專案所使用的開發環境不一定相同，用的node.js版本就有很多不同的版本，
這個時候就可以使用`NVM`來輕鬆切換不同版本的node.js，來解決不同版本所產生的問題。

`NVM` 為 `Node Version Manager` 的縮寫 ， 意思就是 `Node.js的版本管理器`

常使用到的功能 : 

* 切換node.js版本
* 安裝不同版本的node.js作為環境




## 下載教學

* Windows
Windows 有提供安裝工具，下載後照著安裝精靈依序完成即可運作，[下載連結](https://github.com/coreybutler/nvm-windows)。


![](https://i.imgur.com/L5YqZZ0.png)


點擊 Download Now!

![](https://i.imgur.com/PM9CM6m.png)

下載當前最新版本，並直接執行安裝


## 指令



### 檢查 版本 

```shell=
nvm -v 
```

### 安裝 最新版本 

```shell=
nvm install latest
```

### 安裝 LTS 版本
lts 為長期支持版本，版本bug較少

```shell=
nvm install lts
```

### 檢查 近期可用版本

```shell=
nvm list available
```

### 安裝 特定版本
```shell=
nvm install {版本號}
```

### 檢視 已安裝版本
```shell=
nvm list
```


### 切換 版本

```shell=
nvm use latest (最新版本)

nvm use lts (長期支持版本)

nvm use {已安裝版本號} (使用已安裝的版本)
```


### 移除 已安裝版本
```shell=
nvm uninstall {已安裝版本號}
```


### [備註] 環境變數不見

[參考網址](https://israynotarray.com/nodejs/20190801/449913843/) 

開啟環境變數 快捷鍵 win + pause (pageUp 上面那顆)

通常預設
```
 C:\Users\{電腦使用者}\AppData\Roaming\npm
```


##### 可查詢版本

[查詢網址](https://nodejs.org/en/blog/release/)