#### 1. ionic launcher icon
- ionic 中执行`ionic cordova resources` 可以制作ionicApp的图标和启动页面，但是有些坑，记录一下

> icon和splash大小限制

- icon.png  1920*1920 
- splash.png 2732*2732 

- 附上[stackoverflow ionic
](https://stackoverflow.com/questions/29013825/ionic-splash-screen-error-unable-to-read-uploaded-image/31399846)
- [一个免费压缩放大图片的网站](http://www.yasuotu.com/)

#### 2. angular 4.x
> [angular官方文档](https://angular.io/guide/quickstart);

 1. 安装脚手架`npm install -g @angular/cli`
 2. 新建项目`ng new my-app`
 3. cd 到项目中 `npm install` 安装依赖
 4. 启动项目 `ng serve --open`
 
> angular项目目录结构
 
 - e2e (end to end)端对端测试
 - node_modules 安装的第三方模块(npm install生成)
 - src 我们项目的所有文件
   - app  组件 app.modulse.ts 定义根模块
   - assets 静态济源
   - environments 为各个目标环境准备的文件