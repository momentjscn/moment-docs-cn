---
title: date()
version: 1.0.0
signature: |
  moment().date(Number);
  moment().date(); // 数字
  moment().dates(Number);
  moment().dates(); // 数字
---


获取或设置月份的日期。

接受 1 到 31 之间的数字。
如果超出范围，则它将会冒泡达到月份。

注意：`Moment#date` 是月份的日期，而 `Moment#day` 是星期几。

注意：如果链接多个操作以构造一个日期，则应从年份、月份、日期等依次开始。
否则，可能会得到意外的结果，例如，当 `day=31` 并且当前月份只有 30 天时（同样适用于原生 JavaScript `Date` 的操作），返回的日期将会为当前月份的 30 号（有关详情，参阅[月份][get-set_month]）。


错误：`moment().date(day).month(month).year(year)`

正确：`moment().year(year).month(month).date(day)`

**2.16.0** 起废弃使用 ``moment().dates()``。
改用 ``moment().date()``。

