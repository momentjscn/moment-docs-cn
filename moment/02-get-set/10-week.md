---
title: week()
version: 2.0.0
signature: |
  moment().week(Number);
  moment().week(); // 数字
  moment().weeks(Number);
  moment().weeks(); // 数字
---


获取或设置年份的星期。

由于不同的语言环境对年份中的星期的编号的定义不同，因此 Moment.js 添加了 `moment#week` 以获取/设置年份的本地化星期。

年份的星期取决于哪一天是星期的第一天（星期日、星期一等），以及哪一周是年份的第一周。

例如，在美国，星期日是星期的第一天。 
1 月 1 日所在的星期是年份的第一周。

在法国，星期一是星期的第一天，且 1 月 4 日是年份的第一周。

`moment#week` 的输出将会取决于 moment 的[语言环境][i18n]。

当设置年份的星期时，将会保留星期几。

