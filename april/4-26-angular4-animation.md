#### 1.angular4.x动画 animation模块
- [贝塞尔曲线](http://cubic-bezier.com/)
- [angular5 doc animation query](https://www.angular.cn/api/animations/query)

- 1.安装animations模块

```
npm install @angular/animations --save
```
- 2. 页面.ts中导入模块

```
import { trigger, state, style, transition, animate, keyframes, query, stagger } from '@angular/animations';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations/animations';

```

> trigger 触发器

```
  animations: [
    trigger("myAnimationTrigger", [
      state(...),
      state(...),
      transition(...),
      transition(...)
    ])
  ]
```


