---
title: Browserify
---


```
npm install moment
```

```javascript
var moment = require('moment');
moment().format();
```

注意，有一个 bug 会导致无法加载 `moment.locale`。

```javascript
var moment = require('moment');
moment.locale('cs');
console.log(moment.locale()); // en
```

使用下面的解决方法。

```javascript
var moment = require('moment');
require('moment/locale/cs');
console.log(moment.locale()); // cs
```

为了包含所有的语言环境。

```javascript
var moment = require('moment');
require("moment/min/locales.min");
moment.locale('cs');
console.log(moment.locale()); // cs
```
