---
title: vite 專案項目中 使用 @ 代替 src
tags: 
  - vite
  - vue 
  - typescript
categories: vite
date: 2023/11/04 04:50
update: 2023/11/04 04:50
---

## tpyescript

安裝 `@types/node`
 
```
yarn add @types/node
```

```typescript!
import { defineConfig } from 'vite'
import path from 'path';

export default defineConfig({
  ...
  
  resolve: {
    alias: {
      '@': path.resolve(__dirname, 'src'),
    },
  },
  
  ...
  
})

```

在 `tsconfig.json` 中設置

```json!
{
  "compilerOptions": {
    "paths": {
      "@/*": [
        "./src/*"
      ]
    },
  }
}

```