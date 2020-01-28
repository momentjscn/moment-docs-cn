---
title: 操作
---


一旦有了 `Moment`，则可能需要以某些方式对其进行操作。
有很多方法可以帮助处理此需求。

Moment.js 使用[流式的接口模式][Fluent_interface]，也称为[方法链][Method_chaining]。
这使得可以执行以下疯狂的操作。

```javascript
moment().add(7, 'days').subtract(1, 'months').year(2009).hours(0).minutes(0).seconds(0);
```

注意：moment 是可变的。
调用任何一种操作方法都会改变原始的 moment。

如果要创建副本并对其进行操作，则应在操作 moment 之前使用 `moment#clone`。
[查看有关克隆的更多信息][moment-clone]。

