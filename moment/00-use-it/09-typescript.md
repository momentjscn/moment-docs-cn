---
title: Typescript
version: 2.13.0
---

从 2.13.0 版本开始，Moment 会包含一个 typescript 定义文件。

通过NPM安装。
```
npm install moment
```

导入并在你的 Typescript 文件中使用。
<!-- skip-example -->

```javascript
import * as moment from 'moment';

let now = moment().format('LLLL');
```

如果你在导入时遇到麻烦。

对于 Typescript 2.x，则尝试在 ```tsconfig.json``` 文件中的 ```compileOptions``` 中添加 ```"moduleResolution": "node"```，然后使用以下任何语法：

<!-- skip-example -->

```javascript
import * as moment from 'moment';
import moment = require('moment');
```

对于 Typescript 1.x，则尝试在 ```tsconfig.json``` 文件中的 ```compileOptions``` 中添加 ```"allowSyntheticDefaultImports": true```，然后使用语法：

<!-- skip-example -->

```javascript
import moment from 'moment';
```

**区域设置导入**

若要使用 `moment.locale`，则首先需要导入要使用的语言。

<!-- skip-example -->

```javascript
import * as moment from 'moment';
import 'moment/locale/pt-br';

console.log(moment.locale()); // en
moment.locale('fr');
console.log(moment.locale()); // en
moment.locale('pt-BR');
console.log(moment.locale()); // pt-BR
```
