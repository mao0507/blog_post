---
title: Ngrok 介紹
tags: 
  - tools
categories: tools
date: 2023/08/24 22:00:00
update: 2023/08/24 22:00:00
---


## 前言

當在開發網頁的時候，常常要線上測試畫面是否正常，或是提供線上畫面來DEMO檢驗。

這時候就可能需要自己來架設一個服務，看是要讓其他人連線至開發的主機上，或者是部屬到網
路空間上，如果還沒有要正式上線的話，就要提早負擔主機費用，甚至還需要花時間特別去設定，對於有期限的專案來說，太浪費時間了。

於是我們可以使用 `ngrok` 這個第三方軟體，來快速的幫我們建立一個臨時的對外伺服器。


## 教學

 先進入到 [ngrok官網](https://ngrok.com/)

 ![](https://i.imgur.com/Rh85PE9.png)


 點擊右上方的 登入/註冊

 ![](https://i.imgur.com/DZukL03.png)

 有帳號可以直接登入，或是直接使用 google / github 來連接帳號啟用 

 登入後，會進到ngrok的後台

 ![](https://i.imgur.com/XcbgJoF.png)

 依照作業環境，下載對應的檔案

 * 這邊以windows 作業環境為主

 ![](https://i.imgur.com/d2r1zdj.png)

 將檔案解壓縮，並放到 `C:\Program Files\ngrok` 底下

 然後 打開 進階設定  
 - 打開路徑 `設定/系統/關於/進階系統設定`

![](https://i.imgur.com/mfIXVCO.png)

點選 進階/ 環境變數

![](https://i.imgur.com/cSBEJvS.png)

選擇 Path  並點選編輯


![](https://i.imgur.com/O6CoKNr.png)

點選右側新增，並加入 `C:\Program Files\ngrok`

![](https://i.imgur.com/0LQUQBB.png)

打開終端機，並輸入 `ngrok`

![](https://i.imgur.com/8N4s0C0.png)

有出現內容，表示已經安裝成功

![](https://i.imgur.com/6PeIlY6.png)

回到 ngrok 後台頁面，並照著第二步操作 連接帳號

複製下方指令 並輸入終端機 

![](https://i.imgur.com/J9IWkni.png)

有出現這段文字，表示已經連線成功了

![](https://i.imgur.com/8xUDSqu.png)


## 使用方式 


1.在本地開啟服務，假設服務位置為 `http://localhost:5173`

2.打開終端機 並輸入 `ngrok http 5173` 

出現此畫面表示已經成功開啟 ngrok 並且已經正在運行

![](https://i.imgur.com/EgsYAKA.png)

接著將 `Forwarding` 這段的網址 貼到瀏覽器上

![](https://i.imgur.com/WDHMVKv.png)

按下 `Vite Site` 按鈕

就可以進入到 本機環境的網頁了 ，對外就可以直接連線

每一次重新啟動 ngrok，都會產生一個新的 Forwarding，

除非你有付費的 ngrok 帳號，否則你每次都要重新啟動 ngrok，才能取得新的

如果要停止 ngrok ， 只要按下 `Ctrl + C`