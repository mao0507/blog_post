---
title: eslint 安裝教學
tags: 
    - eslint
categories: [eslint ,JavaScript]
date: 2023/06/06 22:56:00
update: 2023/06/06 22:56:00
---


eslint
===

## 安裝 eslint


安裝方式


```shell
npm install eslint 

yarn add eslint
```


```shell
npm install -g
```

這裡需要注意， 是否要將eslint 安裝在global上，
如果安裝在global上的話，初始化就可以直接下`eslint --init` 來進行初始化，
如果沒有安裝在global上的話，則需要到`package.json`另外設定`script`


## 初始化

* eslint 安裝在 global 上

```shell
eslint --init
```

* 安裝在專案裡
設定 `package.json` 中的 `script`
```json
"scripts": {
    "eslint":"eslint --init"
}
```


執行 eslint 初始化
```
yarn eslint 

npm run eslint
```


## 初始化選項

1. How would you like to use ESLint ? `你想使用 ESLint 來做什麼？`
    - To check syntax only (檢查語法)
    - To check syntax and find problems (檢查語法、找出問題)
    - To check syntax, find problems, and enforce code style (檢查語法、找出問題和強制執行編碼風格)

2. What type of modules does your project use ?  `此專案是用什麼方式導入模組？`
    - JavaScript modules (import/export) (使用 import/export)
    - CommonJs (require/exports) (使用 require/exports)
    - None of these (不使用這些)
3. which framework does your project use ?  `要在此專案用哪個框架 ? `
    - React 
    - Vue.js
    - None of these
4. Does your project use TypeScript ? `要使用 TypeScript 嗎 ? `
    - No
    - Yes
5. Where does your code run ? `要在哪個環境下使用 ?`
    - Browser (瀏覽器)
    - Node (Node)
6. How would you like to define a style for your project ? `要使用何種編碼風格?`
    - Use a popular style guide (依照目前流行編碼規則)
    - Anser questions about your style (回答問題來了解你的風格)
7. Which style guide do you want to follow ?  `你想要選擇哪個風格?`
    - Airbnb
    - Standard
    - Google
    - Xo
8. What format do you want your config file to be in ? `產出的config檔案要用何種格式`
    - JavaScript
    - YAML
    - JSON

回答完後，ESLint會依照回答的項目，檢查所需要的套件，詢問是否要直接幫你安裝
這個階段直接選擇 `Yes`  自動下載就好

* Which package manager do you want to use ? `選擇要使用的套件管理器`
     - npm 
     - yarn 
     - pnpm




完成後 專案會多一個 ` .eslintrc.js`



### 參考

[Day02 | 整齊的程式，讓看的人長命百歲，給我用 ESLint](https://ithelp.ithome.com.tw/articles/10215259)