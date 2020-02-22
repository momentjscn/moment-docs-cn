---
title: hijri
signature: |
  npm install moment-hijri
---

如果要使用 Hijri 日历，则可以使用 `moment-hijri` 插件。 
`moment-hijri` 是基于 [Umm al-Qura][ummulqura] 计算得出的 Hijri 阴历的 moment 插件。
该插件由 [Suhail Alkowaileet][xsoh] 开发。

当安装时，它将会封装 `moment`，且你将可以解析 Hijri 日期。
这是一个简短的示例：

```js
m = moment('1410/8/28', 'iYYYY/iM/iD'); // 解析 Hijri 日期。
m.format('iYYYY/iM/iD [is] YYYY/M/D'); // 1410/8/28 is 1990/3/25
```

该仓库位于 [github.com/xsoh/moment-hijri](https://github.com/xsoh/moment-hijri).
