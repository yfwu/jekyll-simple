---
title: Fluent Python Chap 01
category: Python
layout: post
hidden: true
---

在 The Python Language Reference 的 [Data Model](https://docs.python.org/3/reference/datamodel.html) 中，定義了 83 種，其中有 47 種是運算子。

Special method 的主要功能是讓 interpreter 呼叫。

```python
import collections
Card = collections.namedtuple('Card', ['rank', 'suit'])

class FrenchDeck:
    ranks = [str(n) for n in range(2, 11)] + list('JQKA')
    suits = 'spades diamonds clubs hearts'.split()
    def __init__(self):
        self._cards = [Card(rank, suit) for suit in self.suits
                                         for rank in self.ranks]

    def __len__(self):
        return len(self._cards)

    def __getitem__(self, position):
        return self._cards[position]
```

* special method = 在定義 class 中封裝好，使用者不能直接調用的方法。
* `__getitem___` 實作後，可以支援 slicing / iteration / reverse iteration 等各種方法。
* 標準物件例如 list，其 special method 在 Cython 這類實現中，會直接去存取 C 結構內的欄位，速度非常快。
* 不要自己建立奇怪的 special method 例如什麼 `**foo**``，因爲難保將來被使用到。

```python
from math import hypot

class Vector:
    def __init__(self, x=0, y=0):
        self.x = x
        self.y = y

    def __repr__(self):
        return 'Vector(%r, %r)' % (self.x, self.y)

    def __abs__(self):
        return hypot(self.x, self.y)

    def __bool__(self):
        return bool(abs(self))

    def __add__(self, other):
        x = self.x + other.x
        y = self.y + other.y
        return Vector(x, y)

    def __mul__(self, scalar):
        return Vector(self.x * scalar, self.y * scalar)
```

* `__repr__`： 取得物件的字串表達方式；否則，會表示成 `<Vector object at 0x10e000000>` 這樣。
	* 與 `__str__` 方法不同的是，`__repr__` 會希望儘量回傳成等同於原始碼的格式。
	* 如果只能實現一者，優先考慮 `__repr__`，因爲 interpreter 會在找不到 `__str__` 後調用 `__repr__`。
* 算數運算子回傳新的物件
* `__bool__` 提供給 `bool()` 這個函數呼叫：
	* 使用者自定的類別一般視爲 `True`，除非實做了 `__bool__` 或者 `__len__`。
	* 如果 `__len__` 回傳 0，物件會被視爲 `False`。
	* 在 The Python Standard Library - Built-in Types 中，定義了物件 Boolean 相關的測試。

另一種實作 `__bool__` 的方法：

```python
def __bool__(self):
    return bool(self.x or self.y)
```
