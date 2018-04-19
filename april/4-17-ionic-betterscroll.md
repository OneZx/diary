####  1.如何在ionic3中使用better-scroll

> 安装引入

 1. 项目中安装better-scroll`npm install better-scroll --save`
 2. 在页面组件的ts文件中引入
   + `import BScroll from 'better-scroll'` 注意 BScroll没有`{ }`包着
   
   
 > 代码
 
 3. 在html页中的`ion-content`下新建两层div包裹整个dom结构
   ![](/assets/wrapper.png)
 4. 在scss中`.wrapper`的高度设为定高或者`height:100%;`
 - 最后在ts文件中
 
 ```
   ionViewDidLoad() {
    let wrapper = document.querySelector('.wrapper')
    // 可以不加定时器
    setTimeout(()=>{
      const scroll = new BScroll(wrapper,{
        bounceTime:300,
        click:true
      })
    },500)
  }
 ```

 
 #### 2.flex布局整理
 - [runoob](http://www.runoob.com/w3cnote/flex-grammar.html)
 - [阮一峰flex](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?^%$)
 - Flex是Flexible Box的缩写，意为”弹性布局”，用来为盒状模型提供最大的灵活性。
 
 
 #### 3. better-scroll 文档
 - [better-scroll](https://ustbhuangyi.github.io/better-scroll/)