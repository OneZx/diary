> [better-scroll doc](https://ustbhuangyi.github.io/better-scroll/doc/zh-hans/options.html#probetype)

- 之前一直监听不到滚动事件,后来找文档才发现实例化的时候有这个`probeType`

```
      const scrollh = new BScroll(wraptraindetail, {
        bounceTime: 300,
        click: true,
        probeType:2
      })
```