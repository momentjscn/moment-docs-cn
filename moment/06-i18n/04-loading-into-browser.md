---
title: 加载语言环境 (浏览器)
version: 1.0.0
signature: |
  // 从 2.8.1 开始
  moment.locale(String, Object);

  // 废弃于 2.8.1
  moment.lang(String, Object);
---


在浏览器中加载语言环境仅需要包括语言环境文件。
确保指定字符集以防止编码问题。

```html
<script src="moment.js"></script>
<script src="locale/fr.js" charset="UTF-8"></script>
<script src="locale/pt.js" charset="UTF-8"></script>
<script>
  moment.locale('fr');  // 设置默认/全局的语言环境。
  // ...
</script>
```

有所有语言环境的压缩版本：

```html
<script src="moment.js"></script>
<script src="min/locales.js" charset="UTF-8"></script>
```

为了最大程度地减少 HTTP 请求，请使用 Grunt 任务以自定义的语言环境列表来编译 [Moment][moment_github]：

```bash
grunt transpile:fr,it
```

```html
<script src="min/moment-with-locales.custom.js" charset="UTF-8"></script>
```

如果使用 JSPM 作为插件管理器，则应在 lib 中添加语言环境。

```
import * as moment from 'moment';
import 'moment/locale/fr';
```

注意：语言环境文件是以 [UMD][umd] 风格定义的，因此它们应在所有环境中无缝运行。

