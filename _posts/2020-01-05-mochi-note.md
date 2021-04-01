---
title: Mochi 筆記軟體
layout: post
category: Tools
image: /assets/img/mochi.png
---
這篇文章是個自來廣告：介紹我使用的筆記軟體 Mochi。之所以使用 Mochi，要從兩方面談起。

## 筆記軟體
我試過不少筆記軟體，除了主流的 Evernote / Onenote 以外，也試了偏門的如 Bear / Apple Notes / Simplenote / Dynalist / Quiver 等。作為一個放射科醫師，博學強記是基本要求。但其實自己作筆記肯定沒有 Radiopaedia 或者 STATDx 詳細且全面。另外，我有很多臨牀上遇到的實際案例、主治醫師晨會的統整型講解以及論文討論等，這些也包含也是重要的考試及實戰內容。我需要有個軟體幫我做好「遠外儲」這件事：

1. 必須能容納不少圖片（放射科影像）
2. 必須有增量搜尋的功能（也就是可以一邊打字一邊反饋結果）
3. 支援表格（不需要嵌套）
4. 一鍵匯出功能
5. 筆記互聯

比較一下我曾經用過的幾個 app

| 名稱        | 影像 | 搜尋 | 表格 | 匯出 | 內部互聯 |
| ----------- | :--- | :--- | :--- | :--- | :------- |
| Bear        | +    | +    | -    | +    | +        |
| Dynalist    | +    | +    | -    | +    | +        |
| Simplenotes | -    | +    | +    | -    | -        |
| Evernote    | +    | +    | +    | ?    | +        |
| Apple Notes | +    | +    | +    | -    | -        |
| Mochi       | +    | +    | +    | -/+  | +        |

不過，我最近發現了一款新的筆記軟體叫 [Mochi](https://mochi.card)，作者在 HN 也獲得了不少[迴響](https://news.ycombinator.com/item?id=20029466)。Mochi 在所有項目裏面都能滿足我前面提到的五個需求，不過依然有幾個缺點：

![Mochi](/assets/img/mochi.png)

- 最大的問題：**看起來是個一人團隊，隨時有覆滅的可能。**不過，他的筆記軟體跟內容都是存在本機，然後再雲同步；只要電腦沒壞掉，其實都還是可以使用，只是無法同步筆記而已（可能需要使用別的方法來同步，例如，使用 Dropbox 的「指定資料夾同步」來進行同步到其他電腦）。
- 缺少文檔與教學。
- 快捷鍵跟主題不能修改。

另外很神奇的，app 本身支援英文跟「日文」！不曉得是不是因爲作者在學日文的關係？Mochi 還有幾個不錯的特色：

![Mochi LaTeX](/assets/img/mochi-latex.png)

- 支援 LaTeX 公式
- Dark mode
- 支持行內搜尋
- 支持筆記直接標記爲閃卡！（單向同步）
- 發佈筆記爲公開網頁

## Flashcard
Flashcard（閃卡），是指以問答、填空形式，搭配 [spaced reptition](https://mochi.cards/blog/using-spaced-repetition-to-learn-a-language/)  來強化對特定細節記憶力的工具。最有名的就是 Anki，以及採用了不同演算法的 Supermemo。Anki 本身強大、簡單，界面簡潔同時也有很多套件。我自己也是愛用者，然而，隨着卡片數量增加，我開始有了第六個需求...

## Work the System

![my Mochi](/assets/img/mymochi.png)

平常工作時間被各種臨牀業務切分的極爲零碎，需要有閃卡利用時間讀書。但是平日下班後，很難專心的讀教科書做卡片，所以設計了一套無論如何都會有高品質閃卡（flashcard）產出的系統（system / workflow）：

- 將電子資源（網頁、電子書）文件整份 copy 到 Mochi 內；一邊閱讀、刪除不必要的東西，一邊把「重要的知識」做進 ``---`` 之間。
- 設定一個審覈內容的時間；利用週末精神較好的時候，決定是否保留卡片，並且進行精簡與調整。
- 完成後，添加文件到 deck 中，變成一個能按照遺忘曲線複習的閃卡。
