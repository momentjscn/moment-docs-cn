---
title: Webpack
---

```
npm install moment
```

```javascript
var moment = require('moment');
moment().format();
```

默认情况下，webpack 会打包所有的 Moment.js 语言环境（在 Moment.js 2.18.1 中，最小为 160 KB）。 
若要剥离不必要的语言环境且仅打包使用的语言环境，则添加 [`moment-locales-webpack-plugin`][moment-locales-webpack-plugin]：

<!-- skip-example -->

```javascript
// webpack.config.js
const MomentLocalesPlugin = require('moment-locales-webpack-plugin');

module.exports = {
    plugins: [
        // 剥离除 “en” 以外的所有语言环境。
        new MomentLocalesPlugin(),

        // 或者：剥离除 “en”、“es-us” 和 “ru” 以外的所有语言环境。
        //（“en” 内置于 Moment 中，无法移除）
        new MomentLocalesPlugin({
            localesToKeep: ['es-us', 'ru'],
        }),
    ],
};
```

还有其他资源可以使用 webpack 优化 Moment.js，[例如该资源][how-to-optimize-momentjs-with-webpack]。

