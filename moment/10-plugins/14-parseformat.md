---
title: parseformat
signature: |
  npm install moment-parseformat
---


该插件提取日期/时间字符串的格式。

```javascript
var format = moment.parseFormat('Thursday, February 6th, 2014 9:20pm');
// dddd, MMMM Do, YYYY h:mma
moment().format(format); // 格式化
```

这样就可以创建智能日期输入，让用户设置日期/时间，并提取用户的首选格式以供将来使用。
在 [minutes.io][minutes.io] 上找到其用法示例。

该插件由 [@gr2m][gr2m] 编写。 
链接：[演示][moment-parseformat_demo] | [源代码][moment-parseformat]。

