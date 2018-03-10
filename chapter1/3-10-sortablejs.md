> 今天在弄拖拽排序，推荐一个非常好用的插件

* [Sortable.js-github](https://github.com/RubaXa/Sortable)

- 以下是自己写的小demo

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<style>
html{
     background: #F4E2C9;
}
ul,li{
    margin: 0;
    padding:0;
    list-style:none;
}
.wrap{
    width:360px;
    height: 400px;
    position: relative;
    margin: 100px auto;
}
.sort{
    position: relative;
    width: 360px;
    height: 300px;
    overflow: auto;
    margin: 100px auto;
}
.sort ul,li{
    background: white;
}
ul{
    padding: 5px 0;
    max-width: 360px;
    margin: 0 auto;
    text-align: center;
    background-color: #fff;
}
.save{
    color: #fff;
    padding: 3px 10px;
    display: inline-block;
    position: absolute;
    background-color: #FF7373;
    right: 0;
    top: -28px;
    z-index: 1000;
}
</style>
<body>
<div class="wrap">
<div class="save">保存</div>
<div class="sort">
<!--     <ul id="a1">
        <li>item a1</li>
        <li>item a2</li>
        <li>item a3</li>
    </ul>
    <ul id="b1">
        <li>item b1</li>
        <li>item b2</li>
        <li>item b3</li>
        <li>item b4</li>
        <li>item b5</li>
    </ul> -->
    <ul id="c1" style="text-align: center;">
        <li data-id="1"><span>1</span>item c1</li>
        <li data-id="2"><span>2</span>item c2</li>
        <li data-id="3"><span>3</span>item c3</li>
        <li data-id="4"><span>4</span>item c4</li>
        <li data-id="5"><span>5</span>item c5</li>
        <li data-id="6"><span>6</span>item c6</li>
        <li data-id="7"><span>7</span>item c7</li>
        <li data-id="8"><span>8</span>item c8</li>
        <li data-id="9"><span>9</span>item c9</li>
    </ul>        
<div>
</div>
<script src="sortable.js"></script>
<script>
// var a1 = document.getElementById('a1');
// var sortableA = new Sortable(a1, {
//     group:'a1',
//     dataIdAttr: 'data-id',
//     animation: 150,
// })
// var b1 = document.getElementById('b1');
// var sortableB = new Sortable(b1, {
//     group:'b1',
//     animation: 150,
// })
var c1 = document.getElementById('c1');
var sortableC = new Sortable(c1, {
    group:'c1',
    animation: 150,
    // store:{    
    //  /**
    //      * Get the order of elements. Called once during initialization.
    //      * @param   {Sortable}  sortable
    //      * @returns {Array}
    //      */

    //     get: function (sortable) {
    //         var order = localStorage.getItem(sortable.options.group.name);
    //         return order ? order.split('|') : [];
    //     },
    //     set: function (sortable) {
    //         var order = sortable.toArray();
    //         localStorage.setItem(sortable.options.group.name, order.join('|'));
    //     }
    // },
  onStart:function(evt){ //开始拖拽时
    orderStart = sortableC.toArray();
    console.log(orderStart+'-------------startorder')
    console.log(evt)
   console.log(evt.oldIndex+'--------------------oldIndex');
  },
  onEnd: function(evt){ //拖拽完毕之后发生该事件
    var order = sortableC.toArray();
   console.log(evt)
   console.log(evt.newIndex+'--------------------newIndex')
   console.log(order+'-------------------endstart');
  }    
})
</script>
</body>
</html>
```
- 同时附上一篇介绍Sortable.js的技术博客
- [html5 Sortable.js 拖拽排序源码分析](https://www.cnblogs.com/hao123456/p/6025015.html)

---
前端需要学习什么移步：
- [Front-End Developer Handbook 2018](https://github.com/FrontendMasters/front-end-handbook-2018)
- [部分知识点](https://github.com/Erichain/Front-End-Interview-Points)


