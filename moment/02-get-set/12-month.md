---
title: month()
version: 1.0.0
signature: |
  moment().month(Number|String);
  moment().month(); // 数字
  moment().months(Number|String);
  moment().months(); // 数字
---


获取或设置月份。

接受 0 到 11 之间的数字。
如果超出范围，则它将会冒泡到年份。

注意：月份是零索引的，因此一月是月份 0。

从 **2.1.0** 版本开始，还支持月份名称。
这是在 moment 的当前区域设置中解析的。

```javascript
moment().month("January");
moment().month("Feb");
```

在 **2.1.0** 版本之前，如果 moment 更改了月份，且新的月份没有足够的天数来保留该月份的当前日期，则它将会溢出到下个月份。

从 **2.1.0** 版本开始，已将其更改为限制在目标月份的月末。

```javascript
// 2.1.0 之前
moment([2012, 0, 31]).month(1).format("YYYY-MM-DD"); // 2012-03-02
// 2.1.0 之后
moment([2012, 0, 31]).month(1).format("YYYY-MM-DD"); // 2012-02-29
```

**2.16.0** 废弃使用 ``moment().months()``。
改用 ``moment().month()``。

