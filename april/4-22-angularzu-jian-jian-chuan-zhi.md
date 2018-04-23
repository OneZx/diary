#### 父子组件传值@input
1.父组件调用子组件的时候传入数据
```
<i-header [msg]="msg"></i-header>
```
2.子组件引入input模块
```
import { Component, Input } from '@angular/core';
```