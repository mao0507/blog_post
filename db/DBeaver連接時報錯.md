---
title: DBeaver連接時報錯：Public Key Retrieval is not allowed Public Key Retrieval is not allowed
tags: 
  - dataBase 
  - dbeaver
categories: dataBase
date: 2023/07/25
update: 2023/07/25
---

### 解決辦法


1. 找對對應無法連線資料庫

![](https://i.imgur.com/cgwisna.jpg)


2. 對其點擊右鍵 或是按下 F4

  - 如果使用右鍵點擊，需再選擇 `Edit Connecttion`
  ![](https://i.imgur.com/AL9gCL4.jpg)

  - 點開會出現此視窗，(F4也會出現此視窗)
  ![](https://i.imgur.com/mCgag08.jpg)

3. 切換至 Driver properties

![](https://i.imgur.com/XbZ1S0z.jpg)

4. 將 `allowRublicKeyRetrueval` 屬性切換為 True
![](https://i.imgur.com/Voe7OW2.jpg)

5. 按下OK，重新測試連線