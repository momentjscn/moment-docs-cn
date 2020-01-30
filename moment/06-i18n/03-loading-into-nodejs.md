---
title: 加载语言环境 (NodeJS)
version: 1.0.0
signature: |
  moment.locale(String);
---

在 NodeJS 中加载语言环境非常简单。 
如果 `moment-root/locale/` 中有一个以该键命名的语言环境文件，则对 `moment.locale` 的第一次调用将会加载该文件。

```javascript
var moment = require('moment');
moment.locale('fr');
moment(1316116057189).fromNow(); // il y a une heure
```

如果希望你的语言环境受支持，则使用[所需的语言环境和单元测试文件][moment-adding-locale]创建一个对 `develop` 分支的 pull request。

