---
title: jalaali
signature: |
  npm install moment-jalaali
---


如果要使用 Jalaali 日历系统（Jalali、Persian、Khorshidi 或 Shamsi），则可以使用 Behrang Noruzi Niya 的插件 `moment-jalaali`。

当安装后，它会封装 `moment`，且 moment 将可以格式化和解析 Jalaali 的年月。
这是一个简短的示例：

```js
var m = moment('1360/5/26', 'jYYYY/jM/jD'); // 解析 Jalaali 日期。
m.format('jYYYY/jM/jD [is] YYYY/M/D'); // 1360/5/26 is 1981/8/17
```

该仓库位于 [github.com/behrang/moment-jalaali][moment-jalaali]。
