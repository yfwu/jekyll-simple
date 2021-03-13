---
layout: post
title:  "又双叒叕搞了個 Jekyll 部落格"
date: 2021-03-12
categories: tools
---
經過了漫長的實驗，這次是認真的要搞個長長久久的部落格。不過，這次主要是作為一個 RSS 的轉介工具。這個部落格可能會有點像是《社群網戰》電影裡面，男主角用來紀錄雜想的那種很流水式的部落格；或者把它視為長文版的 Twitter 也可以。預期會發布的內容有：

- 每週 Twitter 摘錄（類似周記）
- 在 Obsidian Publish 上面發布的筆記摘錄
- 簡單的動畫、遊戲評論

大概是這樣。另外，這次嘗試了結合了兩種襯線字體 - Roboto Slab 跟 Hiragino Mincho 的組合，看看效果如何，之後再來調整。我期待部落格會有點像「單頁」模式，也就是讀者不需要一則則點開，就可以快速瞄過內容。

底下測試數學式跟程式碼 - 雖然我應該不會用這個部落格發相關的資料，但是沒有添加這些功能就覺得不完整 XD


`R` and `Rstan`:

``` R
data {
  int N;
  int x[N];
  int offset;
}

transformed data {
  int y[N];
  for (n in 1:N)
    y[n] = x[n] - offset;
}
```


$$
  \begin{pmatrix} 1&0\\ 0&2   
  \end{pmatrix}   
  \begin{pmatrix} \epsilon&b'\\ 0&\eta   
  \end{pmatrix}   
  \begin{pmatrix} 1&0\\ 0&2   
  \end{pmatrix}   
  ^{-1} =
  \begin{pmatrix} \epsilon&b'/2\\ 0&\eta   
  \end{pmatrix}
$$