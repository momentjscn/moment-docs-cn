---
title: 取值/赋值
---

Moment.js 使用重载的 getter 和 setter 方法。 
此模式类似与其在 jQuery 中的使用。

不带参数调用这些方法会作为 getter，而带参数调用则会作为 setter。

这些会映射到原生 `Date` 对象上的相应函数。

```javascript
moment().seconds(30).valueOf() === new Date().setSeconds(30);
moment().seconds()   === new Date().getSeconds();
```

如果处于 [UTC 模式][manipulating_utc]中，则它们将会映射到 UTC 的等效项。

```javascript
moment.utc().seconds(30).valueOf() === new Date().setUTCSeconds(30);
moment.utc().seconds()   === new Date().getUTCSeconds();
```

为了方便起见，从 **2.0.0** 版本开始，单数和复数的方法名称都会存在。

注意：当作为 setter 使用时，所有这些方法在都会改变原始的 moment。

注意：从 **2.19.0** 开始，将 `NaN` 传给任何 setter 都是没有操作的。 
在 **2.19.0** 之前，它以错误的方式使 moment 无效。

