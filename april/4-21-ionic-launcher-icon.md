#### 1. ionic launcher icon

* ionic 中执行`ionic cordova resources` 可以制作ionicApp的图标和启动页面，但是有些坑，记录一下

> icon和splash大小限制

* icon.png  1920\*1920 
* splash.png 2732\*2732

* 附上[stackoverflow ionic  
  ](https://stackoverflow.com/questions/29013825/ionic-splash-screen-error-unable-to-read-uploaded-image/31399846)

* [一个免费压缩放大图片的网站](http://www.yasuotu.com/)

#### 2. angular 4.x

> [angular官方文档](https://angular.io/guide/quickstart);

1. 安装脚手架`npm install -g @angular/cli`
2. 新建项目`ng new my-app`
3. cd 到项目中 `npm install` 安装依赖
4. 启动项目 `ng serve --open`

> angular项目目录结构

* e2e \(end to end\)端对端测试
* **node\_modules** 安装的第三方模块\(npm install生成\)
* **src** 我们项目的所有文件
  * app  `组件 app.modulse.ts 定义根模块`
  * assets `静态济源`
  * environments `为各个目标环境准备的文件`
  * **index.html** `主页面的html`
  * **main.ts** `这个应用的主要入口`
  * **styles.css** `全局样式`
  * test.ts `单元测试的主要入口`
  - favicon.icon `浏览器上面的小图标`
* angular-cli.json  `angular-cli的配置文件`
* editorconfig `给编辑器看到简单配置文件`
* .gitignore `git配置文件`
* karma.conf.js `给karma的单元测试配置`
- **package.json** `npm配置文件`
* protractor.conf.js `给protractor使用的端到端测试配置文件`
* README.md `项目说明文档`
* tsconfig.json `TypeScript编译器的配置`
* tslint.json `tslint的配置`

#### angular 创建自定义组件
> [angular中文网](https://www.angular.cn/guide/quickstart)

- `ng g component components/header`

> 绑定属性

```
// 两种都可以 建议第二种
<p  [title]='msg'>{{username}}</p>
<p title='{{msg}}'>{{username}}</p>

```
> 声明属性的几种方式

```
  // public 表示共有 可以在这个类里面和外面使用
  // protected 保护类型  只有在当前类和它的子类里面可以访问
  // private  私有  只有在当前类才可以访问这个属性
  
    title = '这是news'; /*属性定义*/
  id = '123';
  msg: any; /*另一个定义属性的方法*/

  news = '这是string类型的news';

  // 定义属性还可以给他添加修饰符 不加时默认public
  public username = '张三';

```

> 数据循环

1. *ngFor 普通循环

```
<ul>
  <li *ngFor='let item of list'>
    {{item}}
  </li>
</ul>
```
```
// 获取索引值
<ul>
  <li *ngFor='let item of list;let key=index'>
    {{item}}~~~~{{key}}
  </li>
</ul>

// 二维数组 要用嵌套循环出来
<ul>
    <li *ngFor="let item of list4; let key=index">

        {{item.catename}}---{{key}}

        <ol>
            <li *ngFor="let car of item.list">

               -- {{car.title}}
            </li>
        </ol>
    </li>
</ul>
```

> 条件判断

```
<div *ngIf='flag'>flag=true的情况下显示</div>
<br>
<button (click)='flag=!flag'>改变flag的值</button>
```
> 事件对象

```
<input type="text" (keyup)="keyupFn($event)">

  keyupFn(e) {
    console.log(e);
    if (e.keyCode === 13) {
      console.log('按回车了');
    }
  }

<button (click)="run($event)">事件对象</button>

  run(e) {
    console.log(e);
  }
```

> 双向数据绑定[]

- 注意引入FormsModule
```
app.module.ts 中,然后imports中
import { FormsModule } from '@angular/forms';

  /*当前的项目依赖哪些模块*/
  imports: [
    BrowserModule,
    FormsModule
  ],
```

```
<!-- 双向数据绑定 -->
<input type="text" [(ngModel)]="search" />

<p>{{search}}</p>

```