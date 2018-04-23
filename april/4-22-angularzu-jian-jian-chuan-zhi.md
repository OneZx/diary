#### 父子组件传值@input
 1. 父组件调用子组件的时候传入数据
```
<i-header [msg]="msg"></i-header>
```
 2. 子组件引入input模块
```
import { Component, Input } from '@angular/core';
```
 3. 子组件中@Input接收父组件传过来的数据

```
子组件中
export class IHeaderComponent {

  // 通过input接收父组件传来的title值
  @Input() title:string;

  constructor(
    public navCtrl: NavController,
    public navParams: NavParams,
  ) {
```
 4. 