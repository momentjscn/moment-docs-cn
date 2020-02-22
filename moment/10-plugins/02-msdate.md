---
title: msdate
---


如果你在 .NET 中使用 OLE Automation 日期，则查看 Markit On Demand 的 `moment-msdate`。 
使用此插件，可以将 OA 日期格式化为 JavaScript 日期，反之亦然。

将 `moment` 转换为 OA 日期：

```javascript
moment().toOADate(); // 浮点数
```

或者，将 OA 日期转换为 `moment`：

```javascript
moment.fromOADate(41493); // Wed Aug 07 2013 00:00:00 GMT-0600 (MDT)
```

更多信息和详细文档可以在 GitHub 上找到 [http://markitondemand.github.io/moment-msdate/][moment-msdate]。

