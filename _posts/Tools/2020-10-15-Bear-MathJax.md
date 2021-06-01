---
title: 在 Bear 匯出的 HTML 中使用 MathJax
category: Tools
layout: post
---

在頭部 `<head></head>` 裏面嵌入 MathJax 的 CDN script link 如下：

``` html
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
```

然後用 `$$` 把數學式包起來。

$$
x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}
$$
