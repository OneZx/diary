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
  
  // 初始化构造
  // 自定义组件component没有生命周期函数
  ngAfterContentInit() {
    //Called after ngOnInit when the component's or     directive's content has been initialized.
    //Add 'implements AfterContentInit' to the class.
    
  }
```

> 传参

- more.ts 中传值

```
gotoDataList(type) {
  this.navCtrl.push(userdatalistPage, {"dataType":type})
}
```
- userdatalist.ts接收
dataType:string;

constructor(
  public navParams:NavParams
){
  this.dataType = navParams.get('dataType')
}

#### vs code 插件
- 让图片在scss、html的路径中预览
- `image preview`

#### ionic 图片路径
> css使用`../assets/`开头 打包后在web端和app都能看见

```
        .phone{
            background: url(../assets/icons/trainclass/phone.png);
            background-size:contain;   
        }
```

> 在pages/developing/develop.html中 

- 用`assets/` ,前面不要加`/`,注意
- `../assets`不行 `../../assets`不行
```
<img src="assets/icons/common/wait.gif" alt="">
```

#### app图标
- [ios-icon-gallary](http://www.iosicongallery.com/)

#### 移动端适配rem
- 移动端以rem为单位时，设置html字体大小为62.5%（chrome默认字体大小16px） 1rem刚好等于10px， 但调试的时候按chrome最小字体12px计算，1rem=12px。 这时设置`html font-size：10px`,并将chrome最小字体改为10px就好了 (手机上不影响)。

> rem px

- [px2rem](https://www.w3cplus.com/preprocessor/sass-px-to-rem-with-mixin-and-function.html)
- [掘金flexible.js](http://caibaojian.com/flexible-js.html)
- [viewports剖析 ppk](https://www.w3cplus.com/css/viewports.html)
- [Flexible实现手淘h5页面](https://github.com/amfe/article/issues/17?utm_source=caibaojian.com)
- [如何在Vue项目中使用vw实现移动端适配](https://www.w3cplus.com/mobile/vw-layout-in-vue.html)