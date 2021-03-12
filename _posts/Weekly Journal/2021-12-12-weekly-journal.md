---
title: "2021-12-12 週記"
layout: post
category: "Weekly Journal"
---

趕工年底前要交出去的科技部計畫！忙盲茫！這個月都沒有讀國考的東西呀！

## Purely Functional Data Structures

在某個推友分享的連結看到這本書。作者是 Chris Okasaki，書擴編修改自他的博士論文（發表於 1996 年），介紹如何通過「不可變」的概念和函數式程式設計來進行資料結構的設計。看了一下，裡面的範例似乎使用 Standard ML 作為主要語言。也來學習一下怎樣設計跟操作 FP 風格的資料結構來解決演算法問題。

## 閱讀記錄

改成「主概念」、「補充概念」、「人物」以及「行動」組合的模式。補充概念是原本「讀一本書記八張卡片」的「術語卡」的修改版本，跟我的思考方式也比較接近。另外也打算修改 Xdite 的超人閱讀術中提到的十六格筆記法。我覺得讀書最重要的事情是：**如果不能拓展或打破現有認知的疆界，這書就白讀了**；為此，儘快知曉自己所不知道的事物才是讀書的第一要務（按 Xdite 的說法是：像是在搜尋引擎回報的資料中尋找自己需要的），而不是做小卡片、精美筆記、歸檔、互連結什麼的。

## Write Code Every Day

出處是[同名文章](https://johnresig.com/blog/write-code-every-day/)，作者是工程師 John Resig。他在文章中提到，原本他做 side project 的模式是週末趕工，後來發現這樣的模式反而會讓很多 side project 胎死腹中。原因有幾個，例如：

- 妄想在週末的一個晚上完成許多高品質的工作是很困難的。
- 上下文切換的成本高昂（忘記上週程式碼的進度）。

所以他制定了幾條規則：

- 每天為程式碼推進進度：必須是真實的程式碼，不能是重構（refactoring）、文檔（documentation）或部落格。
- 必須是在午夜前寫好且上傳 Github。

在成功的每日寫程式二十週之後，他總結到：每天有所推進對於緩解「進度」所帶來的焦慮感十分有幫助，並且讓腦中「隨時有事做」，大幅改善零碎時間利用效率；在週末進行更多的娛樂活動罪惡感也較低。

## OneDrive client for Linux

如果要在自己的主機間同步程式碼，除了通過 SFTP 或 rsync 連線外，也可以考慮用雲硬碟。目前我有購買 Office 365，所以傾向使用 OneDrive。有個開源的客戶端 [OneDrive Client for Linux](https://github.com/abraunegg/onedrive)。