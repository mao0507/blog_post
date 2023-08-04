---
title: vue3重新渲染元件的方式
tags: 
  - vue 
  - vue3 
  - JavaScript
categories: vue
date: 2023/08/05  03:24:00
update: 2023/08/05 03:24:00
---



> Vue3 rerender a component

1. v-if 
透過v-if的判斷，將組件移除後，重新創立，掛載。


2. 鍵值改變驅動Key-Changing
只需要在component上，綁定key值，就可以透過key值的改動，觸發component的更新

```html
<template>
    <component :key="componentKey" />
</template>
```

```javascript
import { ref } from 'vue';
const componentKey = ref(0);

const Rerender = () => {
  componentKey.value += 1;
};
```