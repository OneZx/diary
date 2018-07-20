- 全新的命令行工具 AngularCli
- 服务端渲染
- 移动和桌面兼容 ionic native
- angular Material 官方UI组件 https://material.angular.io/components/slider/overview

####angular架构

> 组件

- 是angular应用的基本构建块,可以把组件理解为带有业务逻辑和数据的html,
- 组件可以调用服务 Service `服务service`可以用来封装可重用的业务逻辑 
- 服务也可以调用服务
- 指令:允许你想html元素添加自定义行为
- 模块 用来将应用中不同的部分组成一个angular框架可以理解的单元(组件 服务 指令用来完成功能)(构成模块)

#### 环境搭建
1. 全局安装angular cli  `npm install -g @angular/cli`
2. 创建新项目 `ng new my-app`
3. 启动服务  `cd my-app`  `ng serve -o` -o会自动打开浏览器 localhost:4200

> npm 淘宝镜像设置

- `npm config set registry https://registry.npm.taobao.org`
- 还原 `npm config set registry https://registry.npmjs.org`

####angular 组件
```
app.component.ts -- 组件类文件  the component class code ,written in TypeScript
app.component.html - 组件模板
app.component.css - 组件私有css样式
```

- **装饰器** 
```
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
```
- `@Component`是一个装饰器函数,用于为该组件指定angular所需的元数据
- CLI 自动生成三个元数据属性

```
selector— 组件的选择器（CSS 元素选择器）

templateUrl— 组件模板文件的位置。

styleUrls— 组件私有 CSS 样式表文件的位置。

```
- **模板** Template
通过组件自带的模板定义组件的外观(html),可以在模板中使用angular的数据绑定语法
- **控制器** Controller  和 Template 数据绑定
控制器是一个普通的ts类,包含组件所有的属性和方法
```
export class AppComponent {
  title = 'app';
// 在AppComponent 中添加一个`title`属性
    hero:Hero = {
        id:1,
        name:'windstorm'
    }
}
    constructor(){}
```
> export class Component{} 中

**可选的可注入对象 **
- 输入属性 @inputs()
- 提供器 providers  做依赖注入的
- 生命周期钩子 Lifecycle Hooks

**可选的输出对象**
- 生命周期钩子 Lifecycle Hooks
- 样式表 styles
- 动画 Animations
- 输出属性 @Outputs

#### 模块 Module   app.module.ts
一个模块也是带有装饰器的typescript类 @NgModule({})
```ts
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    // declarations 声明模块中有什么  只能声明组件、指令、管道
    AppComponent
  ],
  imports: [
  // 声明要让应用(模块)正常运转,还需要什么,引入其他模块
    BrowserModule
  ],
  providers: [],  // 声明模块中提供了什么服务 ,这里只能声明服务
  bootstrap: [AppComponent]  // 声明了模块的主组件
})
export class AppModule { }
```