---
title: vscode設定Markdown觸發使用者程式碼片段
tags: 
  - vscode
categories: vscode
date: 2023/08/05 03:44
update: 2023/08/05 03:44
---


### 起因
在用markdown寫blog的時候，文章都要先寫一些 `title`、`tags`、`categories` 等...
<br>
建置的時候才能夠順利分類，每一次都要手動打字也太累
<br>
於是想到vscode裡面有 使用者程式碼片段功能，可以幫助我們 快速建立好範本


### 開始建立 個人專屬的 使用者程式碼片段

1. 點選 vscode 左下角齒輪
2. 選擇使用者程式碼片段

![](https://i.imgur.com/02OLlo1.png)

3. 在搜尋欄位中，選擇 `新增全域程式碼片段檔案`

![](https://i.imgur.com/dzK3w3o.png)

4. 建立名稱

![](https://i.imgur.com/mXn7UnU.png)


5. 之後會開啟一個檔案，裡面會有預設的註解

![](https://i.imgur.com/TBLIGCV.png)

6. 以下是自己寫markDown 常使用到的 程式碼片段

```json
{
  "Print to JavaScript code area": {
		"prefix": "!js",
		"body": [
			"```javascript",
			"$1",
			"$2",
			"```",
		],
		"description": "js區塊"
	},
	"Print to css code area": {
		"prefix": "!css",
		"body": [
			"```css",
			"$1",
			"$2",
			"```",
		],
		"description": "css區塊"
	},
	"Print to html code area": {
		"prefix": "!html",
		"body": [
			"```html",
			"$1",
			"$2",
			"```",
		],
		"description": "html區塊"
	},

  "print to blog template" : {
		"prefix": "!blog",
		"body":[
			"---",
			"title: 設定標題",
			"tags: ",
			"  - 設定標籤",
			"categories: 設定歸檔",
			"date: 建立日期",
			"update: 最後更新日期",
			"---"
		],
		"description": "hexo blog 文章建立預設項目"
	}
}
```


7. 建立完成自己的程式碼片段後，需要到vscode 設定去做對應的設定 
  *  開啟 Command Palette (Ctrl+Shift+P)
  * Configure language specific settings
  * 選擇markdown
  * 點選右上角，開啟設定(json)
  * 將下方這段json貼上  ↓
  ```json
  "[markdown]": {
    "editor.quickSuggestions":{
      "other": "on",
      "comments": "on",
      "strings": "on"
    }
  }
  ```

這樣設定就完成了，就可以在markdown使用自己設定好的程式碼片段了 
