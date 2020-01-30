---
title: 设置语言环境 (局部)
version: 1.7.0
signature: |
  // 从 2.8.1 版本开始
  moment().locale(String|Boolean);

  // 废弃于 2.8.1 版本
  moment().lang(String|Boolean);
---


当传递可能需要格式化为不同语言环境的 moment 时，全局的语言环境配置可能会出现问题。

```javascript
moment.locale('en'); // 默认的语言环境为英语。
var localLocale = moment();

localLocale.locale('fr'); // 将此实例设置为使用法语。
localLocale.format('LLLL'); // dimanche 15 juillet 2012 11:01
moment().format('LLLL'); // Sunday, July 15 2012 11:01 AM

moment.locale('es'); // 将全局的语言环境更改为西班牙语。
localLocale.format('LLLL'); // dimanche 15 juillet 2012 11:01
moment().format('LLLL'); // Domingo 15 Julio 2012 11:01

localLocale.locale(false); // 重置实例的语言环境。
localLocale.format('LLLL'); // Domingo 15 Julio 2012 11:01
moment().format('LLLL'); // Domingo 15 Julio 2012 11:01
```

如果不带参数调用 `moment#locale`，则会获取该 moment 使用的语言环境配置。

```javascript
var fr = moment().locale('fr');
fr.localeData().months(moment([2012, 0])) // "janvier"
fr.locale('en');
fr.localeData().months(moment([2012, 0])) // "January"
```

如果需要访问 moment 的语言环境数据，这是首选的方式。

从 **2.3.0** 开始，还可以指定一个语言环境标识符的数组。
它的工作方式与在[全局的语言环境配置][moment_changing-locale]中相同。

