---
title: timer
signature: |
  npm install moment-timer
---


这是一个 Moment.js 插件，允许使用计时器，该计时器比原生的 JavaScript 计时器提供更多的控制权。 
基本上，这是对 JavaScript 自有的 setInterval 和 setTimeout 的重写。

例如，

```javascript
var timer = moment.duration(5, "seconds").timer({loop: true}, function() {
  // 回调
});
```

该仓库位于 [github.com/SeverinDK/moment-timer][moment-timer]。
