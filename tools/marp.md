---
title: Markdown Marp VSCode 套件使用教學
tags: 
  - tools
categories: tools
date: 2023/10/11 15:50:00
update: 2023/10/11 16:30:00
---

## 前言

常常要開會議報告，需要講稿的時候，都還要特別去做PPT或是PDF，對於一個工程師來說，這是一種折磨

可以用順手的工具去做投影片就可以輕鬆很多，也可以省去很多精力

於是就找到了 `Marp` 這個功能套件


## 介紹

`Marp` 是一個基於 Markdown 語法的投影片製作工具。

可以使用 Markdown 語法 快速建立 報告用的投影片


## 什麼是Markdown 

> Markdown是一種輕量級標記式語言，它允許人們使用易讀易寫的純文字格式編寫文件，然後轉換成有效的XHTML文件。

[來源](https://zh.wikipedia.org/zh-tw/Markdown)


## 安裝

有 VsCode 專用套件和 獨立的 CLI 可以做選擇

![](https://i.imgur.com/gyYEoAn.jpg)

`本次以 VsCode 套件為主`

安裝 Marp 非常簡單
只要在 VsCode 中安裝[Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)的 Plugin 即可。


# 基本設定

要在 VsCode 使用 Marp ，
首先我們要在文件最上方加入以下內容：


```
--- 
marp: true 
theme: gaia
paginate: true
---
```

告訴Vscode 我們開始使用 marp的套件了

```java
marp : boolean
```

theme 是指簡報主題的意思，
Marp 預設提供了 3 種簡報主題：
<br>

- Default 預設主題
- uncover 主題具有三個設計理念：簡約、簡約、現代
- Gaia 主題基於[yhatt/marp](https://github.com/yhatt/marp)的經典設計

<br>

每種主題在背景顏色，
Markdown文字的擺放位置都會有差異

[參考說明](https://github.com/marp-team/marp-core/tree/main/themes?source=post_page-----eab8a0668733--------------------------------#readme)


paginate 為 顯示頁數的選項

```java
paginate:boolean
```


## 基本語法

### 1. 分頁

可使用 `---` 標記來分隔不同頁面的 Slide
```markdown
# Page 1
Hello World!

---

# Page 2
Hello World 2!
```

### 2. 設定圖片寬度

```markdown
![width:200px](image_path.jpg) <!-- 設定圖片寬度為 200px -->
![height:300px](image_path.jpg) <!-- 設定圖片高度為 300px -->
![width:200px height:300px](image_path.jpg) <!-- 同時設定兩者屬性 -->
![w:32 h:32](image_path.jpg) <!-- 設定圖片大小為 32x32 px -->
![width:90% height:80%](image_path.jpg) <!-- 設定圖片大小為 90% 寬度 x 80% 高度  -->
```

### 3. 設定圖片特效

```markdown
![blur](image_path.jpg) <!-- 圖片 模糊化  -->
![blur:10px](image_path.jpg) <!-- 圖片模糊化，參數為 10px(越大越模糊)  -->
![grayscale:1](image_path.jpg) <!-- 圖片灰階化  -->
![brightness:.8 sepia:50%](image_path.jpg) <!-- 多重特效設定 -->



### 4. 設定背景圖片
```markdown
![bg](bg.jpg) <!-- 設定 bg.jpg 為背景圖片-->
![bg fit](bg.jpg) <!-- 設定 bg.jgp 的圖片大小調整為背景框架大小 -->
```



### 4.1 控制背景圖位置

```markdown
![bg left](bg.jpg) <!-- 充滿左側畫面 -->
![bg left:33%](bg.jpg) <!-- 充滿左側 33% 畫面 -->
![bg right](https://picsum.photos/720?image=29) <!-- 充滿右側畫面 -->
```
`bg left` 預覽

![bg left](https://i.imgur.com/jJXSHNV.png)

`bg left:33%` 預覽

![bg left:33%](https://i.imgur.com/uJ73gpD.png)

`bg right` 預覽

![bg right](https://i.imgur.com/MDRqycI.png)


### 5. 數學表示式

Marp 支援使用 Latex 語法來撰寫數學式，
只要使用 $...$ 或 $$...$$ 包含著 Latex 數學式
即可透過 Katex 或 MathJax 套件來顯示數學式。
現在我們在 Markdown 中輸入一下 Latex 表示式

輸入 Latex 表示式
```
$$
\sum_{n=0}^{\infty}=\frac{f^{(n)}(a)}{n!}(x-a)^n
$$

```

顯示結果

![](https://i.imgur.com/i7W0FJ7.png)


## 匯出投影片

只要選擇 右上角 兩個三角形圖案

![](https://i.imgur.com/gcu5NZb.png)


選擇 第一項

`export Slide Deck`

![](https://i.imgur.com/bssChVz.png)

就可以順利匯出pdf檔案了


## 總結

`marp` 很方便於常常寫 markDown 文件的人來做使用，
可以將已經寫好的文件直接轉換成投影片，
可以省去時間在那邊拉圖，排版等事情


## 參考資料


- [十分鐘快速掌握 Markdown](https://www.casper.tw/development/2019/11/23/ten-mins-learn-markdown/)
- [Markdown 維基百科](https://zh.wikipedia.org/zh-tw/Markdown)
- [VScode套件](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)
- [官方文件](https://marpit.marp.app/theme-css?id=tweak-style-through-markdown) 
- [Marp 使用細節](https://yfwu.dev/tools/2021/12/13/marp.html)
- [如何快速完成簡報排版，將精神專注在準備演講上？使用 Marp 套件轉換 Markdown 成簡報](https://medium.com/pm%E7%9A%84%E7%94%9F%E7%94%A2%E5%8A%9B%E5%B7%A5%E5%85%B7%E7%AE%B1/%E5%A6%82%E4%BD%95%E5%BF%AB%E9%80%9F%E5%AE%8C%E6%88%90%E7%B0%A1%E5%A0%B1%E6%8E%92%E7%89%88-%E5%B0%87%E7%B2%BE%E7%A5%9E%E5%B0%88%E6%B3%A8%E5%9C%A8%E6%BA%96%E5%82%99%E6%BC%94%E8%AC%9B%E4%B8%8A-eab8a0668733)
- [使用Marp以Markdown快速製作簡報，並匯出HTML、PPTX與PDF](https://jdev.tw/blog/5839/marp-markdown-presentation-writer)
- [用 Markdown 撰寫 Slide - 使用 Marp 套件](https://blog.yeshuanova.com/2021/06/marp_vscode/)
