---
title: shortformat
---

如果要以较短的方式格式化时间，可以使用 [@researchgate][researchgate] 的 [moment-shortformat][moment-shortformat] 插件。

它基于和类似于 moment.twitter 插件，但输出不同。

```javascript
moment().subtract(5, 'hours').short();
// 5h ago
moment().add(5, 'hours').short();
// in 5h
```
您还可以禁用[相对时间模板][moment-relativeTime]的使用：

```javascript
moment().subtract(1, 'hour').short(false);
// 1h
```

如果该日期在将来或过去过长，它将会显示为：

```javascript
moment().subtract(500, 'days').short();
// 5 Mar, 1970
```
