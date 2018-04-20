#### header里fixed的元素居中

![](/assets/fixed.png)

```
// 父元素
.header{
    position:fixed;
    margin:0 auto;
    // 左右居中
    left:0;
    right:0;
    // 上下居中
    top:0;
    bottom:0;
}
```

#### ionic3 中better-scroll 给动态高度内容上下拉扯的效果
- html

```
<ion-content style="background-color:#f5f5f5;" id="ionPage">
  <div class="bg">
    <div class="header">
      <a (click)="goback()">
        <i class="arrow-back"></i>
      </a>
      <p>培训详情</p>
    </div>
  </div>


  <div style="position:relative;top:-4rem;" id="setheight">
    <div class="wrap-traindetail" id="wrap">
      <div class="train-info">
      //后面省略。。。

```

- js

```ts
    //获取整个ion-content的高度
    let ionHeight = document.getElementById('ionPage').offsetHeight;
    //结合better-scroll 
    let wraptraindetail = document.querySelector('.wrap-traindetail');
    // 渲染完后动态获取wrapper的高度（wrapper高度为内容撑开）
    let wrapheight = document.getElementById("wrap").offsetHeight;
    // 让wrapper的父元素高度为wrapper高度-1 px， (wrapper高度为100%；)
    // 当内容超过屏幕高度时，这里有bug，换ionPage高度减去上面高度（+1）这种方式
    let setheight = document.getElementById("setheight");
    //setheight.style.height = wrapheight-1+'px';
    //setheight.style.height = ionHeight-60+'px';
    
    // 当内容超过ionpage视口高度时
    if(wrapheight>=ionHeight-60){
      setheight.style.height = ionHeight-61+'px';
    }else{
      setheight.style.height = wrapheight-1+'px';
    }

    setTimeout(()=>{
      const scroll = new BScroll(wraptraindetail,{
        bounceTime:300,
        click:true
      })
    },100)
  }
```

