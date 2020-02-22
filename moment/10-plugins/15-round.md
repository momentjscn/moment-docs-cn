---
title: round
signature: |
  npm install moment-round
---


For example,
该插件会将日期/时间四舍五入到给定的时间间隔。

例如，

``` javascript
require('moment-round');
var m = new moment(); // 2015-06-18 15:30:19
m.round(5, 'seconds'); // 2015-06-18 15:30:20
m.ceil(3, 'minutes'); // 2015-06-18 15:33:00
m.floor(16, 'hours'); // 2015-06-18 00:00:00
m.ceil(21, 'hours'); // 2015-06-18 21:00:00
m.ceil(20, 'hours'); // 2015-06-19 00:00:00
```

该仓库位于 [github.com/WebDevTmas/moment-round][moment-round]。

