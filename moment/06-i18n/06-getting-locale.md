---
title: locale()
version: 1.6.0
signature: |
  // 从 2.8.1 版本开始
  moment.locale();

  // 废弃于 2.8.1 版本
  moment.lang();
---

如果需要经常更改语言环境，则可能想知道当前正在使用的语言环境。
这可以不带任何参数调用 `moment.locale`。


```javascript
moment.locale('en'); // 设为英语
moment.locale(); // 返回 'en'
moment.locale('fr'); // 设为法语
moment.locale(); // 返回 'fr'
```

从 **2.12.0** 版本开始，可以列出所有已加载并可以使用的语言环境：

```javascript
moment.locales()
```
