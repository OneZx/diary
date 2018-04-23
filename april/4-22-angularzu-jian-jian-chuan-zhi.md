#### 1.父子组件传值@input
1.父组件调用子组件的时候传入数据
 
```
<i-header [msg]="msg"></i-header>
```
2.子组件引入input模块
 
```
import { Component, Input } from '@angular/core';
```
3.子组件中@Input接收父组件传过来的数据

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
4.父组件
 
 ```
 // html
 // [title]='title'后一个title是父组件传来的值,前面的title是子组件定义的接收的名称
<i-header [title]='title'></i-header>
 
 
 // ts
 export class LifePage {

  public title="生活";

  constructor(public navCtrl: NavController, public navParams: NavParams) {
  }
 ```

#### 2.子组件接收父组件传来的方法
1.子组件

```
// 接收父组件传来的run方法
@Input() run;

// 子组件内
  <div class="header" #bgheader (click)="run()">
```
2.父组件

```
// 方法
run(){
 alert('这是home组件的run方法')
}

// html 调用的时候
  <i-header [title]='title' [run]='run'></i-header>
```

#### 3.父组件接收子组件传来的值(用方法)
1.父组件
```
  getDataFromChild(childData){
    alert(childData);
  }
  
  <i-header [title]='title' [run]='run' [getDataFromChild]='getDataFromChild'></i-header>

```

2.子组件
```
// 接收父组件传来的方法
@Input() getDataFromChild 
[getDataFromChild]='getData...';

msginfoChild = '这是子组件的信息'

sendParent(){ // 子组件自己的方法

// 子组件调用父组件的方法
  this.getDataFromChild(this.msginfoChild)
}
```

#### 4. 子组件通过@Output执行父组件的方法
1. 子组件引入Output和EventEmitter
```
<i-header [title]='title' [run]='run'></i-header>
```

2. 子组件中实例化EventEmitter

```
  @Output() private outer=new EventEmitter();
```

3. 子组件通过EventEmitter 对象outer实例广播数据

```
sendParent(){
  this.outer.emit('msg from child')
}
```