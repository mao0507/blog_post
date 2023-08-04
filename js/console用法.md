---
title: console用法
tags: - JavaScript
categories: JavaScript
date: 2023/05/31
update: 2023/05/31
---


## 關於Console

在寫 JavaSrcipt的時候，要檢查運作流程或是檢查變數的狀態的時候，都會用到`console.log`來檢視程式或是參數的值，
但是`console`還有很多不同的用法


- console.log()
- console.info()
- console.warn()
- console.error()
- console.dir()
- console.count()
- console.assert()
- console.table()

<h3 id="log"> console.log() </h3>

這是最常使用到，最基本的用法。<br>

`console.info()`、`console.warn()`、`console.error()`

這幾個的用法也是一樣 <br>

以下為使用方法 :

```javascript=

const str = 'Hello World';

console.log(str);
console.info(str);
console.warn(str);
console.error(str);

```

輸出結果如下 <br>

![](https://i.imgur.com/yRfdzka.png)

<br>
`console.log()` 輸出的是標籤

`console.dir()` 輸出的卻是物件


<h3 id="dir"> console.dir() </h3>

`console.dir()`是一種在控制台中查看指定JavaScript物件的所有屬性的方法，開發人員可以通過這種方式輕鬆獲取物件的屬性。


以下為程式碼 : 

```html
<p id="pp">hello</p>
```

```JavaScript
// 取得html標籤
const pp = document.getElementById('pp')

console.log('---log---')
console.log(pp) // log
console.log('---dir---')
console.dir(pp) // dir

```

輸出結果 <br>
![](https://i.imgur.com/DiYHs3s.png)







<h3 id="count"> console.count() </h3>

測試程式運行邏輯時，我們需要知道一段程式執行了多少次，我們可以使用console.count()來達到我們的目的

```JavaScript
function func() {
    console.count("label");
}

for(let i = 0; i < 3; i++) {
    func();
}
```

輸出結果為 : 
```
label: 1
label: 2
label: 3
```



<h3 id="assert"> console.assert() </h3>

類似測試 條件判斷，當判斷為false 會出現錯誤訊息


以下為程式碼 : 
```JavaScript
const arr = [1, 2, 3];
console.assert(arr.length === 4);
```


輸出結果為
![](https://i.imgur.com/ggFoDLx.png)



<h3 id="table"> console.table() </h3>

可以將物件 轉換成 table的方式顯示

```JavaScript
const people = {
    "person1": {"fname": "san", "lname": "zhang"}, 
    "person2": {"fname": "si", "lname": "li"}, 
    "person3": {"fname": "wu", "lname": "wang"}
};
```


輸出結果

![](https://i.imgur.com/qsuwwHb.png)


~~只是這個轉換時間會比較久~~