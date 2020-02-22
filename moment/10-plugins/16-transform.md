---
title: transform
signature: |
  bower install moment-transform
---

[`moment-transform`][moment-transform_demo] 是一个通过模式操作日期的插件。
可以对 Moment 实例的各个部分（小时、月份等）使用基本操作（设置/添加/减少）。

```js
moment().transform('YYYY-MM-+01 00:00:00.000'); // Tonight at midnight
moment().transform('14:30:00.000'); // Today, 2:30 pm
moment().transform('YYYY-MM--30 00:00:00.000'); // 30 days ago
```

可选的参数可以指定自定义的模式并强制使用严格的模式（默认情况下，在传入的字符串中非字母字符不是必需的）。

```js
moment().transform('+01MMYYYY', 'DD/MM/YYYY', false); // Tomorrow, same time
moment().transform('+01MMYYYY', 'DD/MM/YYYY', true); // Invalid date
```

示例在[这里][moment-transform_demo]，仓库在[这里][moment-transform]。

