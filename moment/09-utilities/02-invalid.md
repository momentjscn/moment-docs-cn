---
title: invalid()
version: 2.3.0
signature: |
  moment.invalid(Object);
---


可以创建自己的无效 Moment 对象，这对于创建自己的解析器很有用。

```javascript
var m = moment.invalid();
m.isValid();                      // false
m.format();                       // 'Invalid date'
m.parsingFlags().userInvalidated; // true
```

`invalid` 还接受一个对象，该对象指定要设置的解析标志。
这不会设置 `userInvalidated` 解析标志，除非它是指定的属性之一。

```javascript
var m = moment.invalid({invalidMonth: 'Actober'});
m.parsingFlags().invalidMonth; // 'Actober'
```

无需指定 Moment 可以识别的解析标志。
但是，Moment 将会是无效的，并且解析标志将会由 `parsingFlags()` 返回。

