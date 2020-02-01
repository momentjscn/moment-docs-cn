---
title: locale('x-pseudo')
version: 2.13.0
signature: | 
    moment.locale('x-pseudo')
---

从 **2.13.0** 版本开始，moment 可选地包含伪语言环境。
此语言环境将会使用非常明显变化的数据填充日期。
伪语言环境在测试时很有用，因为它们可以清楚地显示已定位和未定位的数据。
只需包含伪语言环境，并将 moment 的语言环境设置为 x-pseudo。 
Moment 中的文本将会非常容易发现。

```javascript
moment.locale('x-pseudo');
moment().format('LLL'); //14 F~ébrú~árý 2010 15:25
moment().fromNow(); //'á ~féw ~sécó~ñds á~gó'
moment().calendar(); //'T~ódá~ý át 02:00'
```