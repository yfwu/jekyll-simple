---
title: 在部落格嵌入表格資料
category: Tools
layout: post
---
主要是想要把藏書列出來，但是希望能用 CSV 格式來存放書籍資料（目前書籍資料存在 Google Drive，只要下載為 CSV 即可）。搜尋了一下，發現 Jekyll 確實有[通過模板來呈現資料的功能](https://jekyllrb.com/tutorials/csv-to-table/)。

首先是準備資料，放在 `_data` 下，之後就可以通過 ``{{ site.data.table }}`` 來取用。文章中介紹了如何取用行資料的語法如下：

```
{% assign row = site.data.table[0] %}
{{ row | inspect }}
```

而每行的每個欄位則可以用 hash table 的方式取得：

```
{% assign row = site.data.table[0] %}
{% for pair in row %}
  {{ pair | inspect }}
{% endfor %}
```

以如上語法搭配 HTML tag `<table>` `<tr>` `<th>` 就可以建構表格了。其實 Jekyll 有個 `tablerow` 元件可以用，但是就不會生成所謂的 header row，所以必須自幹。

``` HTML
<table>
  {% for row in site.data.sample %}
    {% if forloop.first %}
      <tr>
        {% for pair in row %}
          <th>{{ pair[0] }}</th>
        {% endfor %}
      </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[0] }}
    {% endtablerow %}
  {% endfor %}
</table>
```

<table>
  {% for row in site.data.sample %}
    {% if forloop.first %}
      <tr>
        {% for pair in row %}
          <th>{{ pair[0] }}</th>
        {% endfor %}
      </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[0] }}
    {% endtablerow %}
  {% endfor %}
</table>
