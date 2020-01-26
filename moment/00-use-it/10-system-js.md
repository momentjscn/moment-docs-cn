---
title: System.js
---

若要加载 moment，则将其放置在 baseURL 配置中的 System.config 指定的路径中。 
然后将其导入页面。

<!-- skip-example -->

```js
<script src="system.js"></script>
<script>
  System.config({
    baseURL: '/app'
  });

  System.import('moment.js');
 </script>
```

如果需要将 moment 加载为全局变量，则可以使用元配置：

<!-- skip-example -->

```javascript
System.config({
  meta: {
    'moment': { format: 'global' }
  }
});
```

另外，若要将 Moment 作为全局仅提供给特定的依赖项，则可以如下操作：

<!-- skip-example -->

```javascript
System.config({
  meta: {
    'path/to/global-file.js': {
      globals: {
        moment: 'moment'
      }
    }
  }
});
```
