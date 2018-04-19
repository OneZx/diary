> ionic组件

- 新建组件 ionic g component [name]
- app.module.ts中引入

```
// 引入自定义components模块
import { ComponentsModule } from '../components/components.module';
```
- 在需要用的地方直接使用 `<line-tips></line-tips>`

> 组件的传值

- [ionic-github](https//github.com/ionic-team/ionic)
- linetips.ts

```
// 导入 Input
import { Component, Input } from '@angular/core';


export class LinetipsComponent {
  text: string;
  // msg 外部传递进来, message 本地接收之后的参数命名
  @Input('msg') message;

  constructor() {

  }
```