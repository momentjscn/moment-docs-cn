---
title: Require.js
---

如果你打算将 moment 与 Require.js 结合使用，则强烈建议你阅读[此内容][requirejs_issues_1554]。 
另外，请升级到 **2.14.0** 或更高版本以获得最佳体验。

首先，你可能需要通过 bower 或 node_modules 或其他方式将 moment.js 以及语言环境目录放置在基层文件夹中来获取 moment。 
然后，你可以使用 [adapt-pkg-main] 之类的工具、或者手动使用[包配置][requirejs_packages_config]。

<!-- skip-example -->

```javascript
requirejs.config({
  packages: [{
    name: 'moment',
    // 此位置是相对于 baseUrl 的。 
    // 选择 bower_components 还是 node_modules 取决于具体的安装方式。
    location: '[bower_components|node_modules]/moment'
    main: 'moment'
  }]
});
```

通过上述的设置，你可以使用 `moment` 引入核心模块、使用 `moment/locale/de` 引入 `de` 语言环境。

<!-- skip-example -->

```javascript
// 只需要核心模块。
define(['moment'], function (moment) {
	console.log(moment().format('LLLL'));  // 'Friday, June 24, 2016 1:42 AM'
});

// 具有单一语言环境的核心模块。
define(['moment', 'moment/locale/de'], function (moment) {
	moment.locale('de');
	console.log(moment().format('LLLL')); // 'Freitag, 24. Juni 2016 01:42'
});

// 具有所有语言环境的核心模块。
define(['moment/min/moment-with-locales'], function (moment) {
	moment.locale('de');
	console.log(moment().format('LLLL')); // 'Freitag, 24. Juni 2016 01:42'
});

// 异步加载语言环境。
define(['require', 'moment'], function(require, moment) {
  // 检测到语言环境之后，在某个模块内部。 
  // 这是在模块加载时间之前不知道语言环境的情况。
  require(['moment/locale/de'], function(localeModule) {
    // 此处已加载语言环境，但尚未使用。
    console.log(moment().format('LLLL'));  // 'Friday, June 24, 2016 1:42 AM'

    moment.locale('de');
    // 已经正确地设置了语言环境之后使用 moment。
    console.log(moment().format('LLLL')); // 'Freitag, 24. Juni 2016 01:42'
  })
});
```

对于更复杂的用例，请阅读 [@jrburke 的出色解释][requirejs_issues_1554]。

Moment 仍将会创建全局的 `moment`，这对于插件和其他第三方代码很有用。 
如果需要制止该全局变量，则在模块配置上使用 `noGlobal` 选项。

<!-- skip-example -->

```javascript
require.config({
    config: {
        moment: {
            noGlobal: true
        }
    }
});
```

如果未指定 `noGlobal`，则全局导出的 moment 将会打印弃用警告。 
从下一个主要版本开始，如果你需要这种行为，则必须自行导出。

对于 **2.5.x** 版本，如果使用依赖 Moment 但与 AMD 不兼容的其他插件，则可能需要在 r.js 配置中添加 [`wrapShim: true`][jrburke_rjs_wrapshim]。

为了使 moment.js 插件可以在 requirejs 环境中被加载，moment 会被创建为一个命名模块。 
因此，必须使用 `paths` 来确定目录，将 moment 完全按 `"moment"` 加载。 
使用 `"vendor\moment"` 之类的路径引入 moment 将会返回 `undefined`。

从 **2.9.0** 版本开始，moment 会将自身导出为匿名模块，因此，如果仅使用核心模块（不使用语言环境或插件），则将其放置在非标准位置时不需要配置。

