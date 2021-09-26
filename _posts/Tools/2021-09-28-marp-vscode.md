---
title: 使用 Marp 來製作投影片
category: Tools
layout: post
---

將 Markdown 文件轉換成投影片的工具很多，不過我最近發現一個特別好用的叫 [Marp](http://marp.app)。主要的優點是，它可以與 VS code 深度結合。只要在 front-matter 裡面寫下：

```markdown
marp: true
theme: uncover
paginate: true
```

即可！（註記：分別是啟用 marp、設定主題、設定頁碼）

具體轉換程式與一些特殊的語法可以參考 [Marp Core](https://github.com/marp-team/marp-core)。主題部分，官方提供的選擇除了預設外還有 Gaia 跟 Uncover 兩組。我個人覺得 Uncover 蠻適合用來做快速簡報的投影片。

其他補充說明：

- 如果要匯出，需要系統有安裝 `marp-cli`
- 預設數學使用 katex
- 自動縮放程式碼跟數學式
- 使用 `---` 作為分頁

底下是官方圖片，借來展示一下：

![Sample](https://marp.app/assets/marp-for-vs-code.png)
