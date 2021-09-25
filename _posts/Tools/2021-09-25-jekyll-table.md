---
title: 在部落格嵌入表格資料
category: Tools
layout: post
---

主要是想要把藏書列出來，但是希望能用 CSV 格式來存放書籍資料（目前書籍資料存在 Google Drive，只要下載為 CSV 即可）。搜尋了一下，發現 Jekyll 確實有[通過 Liquid 模板來呈現資料的功能](https://jekyllrb.com/tutorials/csv-to-table/)。

資料放在 `_data` 下就可以通過 `site.data.table` 來取用。搭配 HTML tag `<table>` `<tr>` `<th>` 就可以建構表格了。其實 Jekyll 有個 `tablerow` 元件可以用，但是就不會生成所謂的 header row，所以必須自幹。

{% assign row = site.data.sample[0] %}
{{ row | inspect }}
