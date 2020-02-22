---
title: twix
signature: |
  npm install twix
---


另一个范围插件是 Isaac Cambron 的库 `Twix`。
它具有许多与范围相关的特性，并且擅长格式化范围。
例如，

```javascript
var t = moment("1/25/1982 9:30 AM").twix("1/25/1982 1:30 PM");
t.isCurrent(); // false
t.count('minutes'); // 241
t.format();  // 'Jan 25, 1982, 9:30 AM - 1:30 PM'
t.simpleFormat("h:m"); // '9:30 - 1:30'
```

所有选项和特性的完整文档在[这里][twix]。

像这样在 npm 上可用：

```
npm install twix
```

或者只是从[这里][twix.js]获取 JS 文件。
