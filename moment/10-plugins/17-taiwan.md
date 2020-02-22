---
title: taiwan
signature: |
  npm install moment-taiwan
---


如果要使用台湾日历系统，可以使用 Bradwoo8621 的插件 `moment-taiwan`。

当安装后，它将会可以封装 `moment`，且将可以格式化和解析台湾年份。 
这是一个简短的示例：

```js
m = moment('104/01/01', 'tYY/MM/DD') // 解析 Taiwan 日期
m.format('tYY/MM/DD [is] YYYY/M/D') // 104/01/01 is 2015/01/01

m.twYear() // 104
```

该仓库位于 [github.com/bradwoo8621/moment-taiwan][moment-taiwan]。
