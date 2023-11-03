---
title: typescript 找不到模組 './App.vue' 或其對應的型別宣告。
tags: 
  - typescript
categories: typescript
date: 2023/11/04 04:50
update: 2023/11/04 04:50
---


## 錯誤訊息 


![](https://i.imgur.com/wGrMi0x.png)


報錯原因：typescript 只能理解 .ts 檔案，無法理解 .vue檔案


## 解決方法 

在專案根目錄專案 或是 `src` 資料夾底下建立一個，不為`main`，字尾為`.d.ts`的檔案

然後加入此段程式碼

```javascript
declare module '*.vue' {
  import { ComponentOptions } from 'vue'
  const componentOptions: ComponentOptions
  export default componentOptions
}
```

![](https://i.imgur.com/jJotjgG.png)
