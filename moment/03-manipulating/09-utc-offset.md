---
title: utcOffset()
version: 2.9.0+
signature: |
  moment().utcOffset();
  moment().utcOffset(Number|String);
  moment().utcOffset(Number|String, Boolean);
---

获取 UTC 偏移量（以分钟为单位）。

注意：与 [`moment.fn.zone`][moment.zone] 不同，此函数返回 UTC 的实际偏移量，而不是反向偏移量（类似 `Date.prototype.getTimezoneOffset` 返回的）。

获取当前对象的 `utcOffset`：

```javascript
moment().utcOffset(); // (-240、-120、-60、0、60、120、240 等)
```

通过提供分钟数来设置 UTC 偏移量。
在调用 `utcOffset()` 的 moment 对象上设置偏移量。
如果想要全局地设置偏移量，则尝试使用 [moment-timezone][moment-timezone]。
注意，一旦设置了偏移量，则它便会固定且不会单独更改（即没有 DST 规则）。
如果想要一个实际的时区（特定位置的时间），例如 `America/Los_Angeles`，则考虑使用 [moment-timezone][moment-timezone]。

```javascript
moment().utcOffset(120);
```

如果输入小于 `16` 且大于 `-16`，则会将输入解释为小时。

```javascript
// 这些是等效的。
moment().utcOffset(8);  // 设置小时偏移
moment().utcOffset(480);  // 设置分钟偏移 (8 * 60)
```

也可以设置字符串的 UTC 偏移量。

```javascript
// 这些是等效的。
moment().utcOffset("+08:00");
moment().utcOffset(8);
moment().utcOffset(480);
```

`moment#utcOffset` 会在字符串中搜索 `+00:00 +0000 -00:00 -0000 Z` 的第一个匹配项，因此甚至可以传入 ISO8601 格式的字符串，且 moment 将会更改为 UTC 偏移量。

注意，如果字符串不是 'Z'，则必须以 `+` 或 `-` 字符开头。

```javascript
moment().utcOffset("2013-03-07T07:00:00+08:00");
```

`utcOffset` 函数具有可选的第二个参数，该参数接受一个布尔值，该布尔值表明是否保留日期中的现有时间。

- 传入 `false`（默认）将会在世界标准时间中保持不变，但本地时间将会改变。

- 传入 `true` 将保留相同的本地时间，但要以在世界标准时间中选择其他时间为代价。

此特性的一种用法是，如果只想使用数字型输入值来构造具有特定时区偏移量的 moment：

```javascript
moment([2016, 0, 1, 0, 0, 0]).utcOffset(-5, true) // 等效于 "2016-01-01T00:00:00-05:00"
```
