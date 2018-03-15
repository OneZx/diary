> 最简单的深拷贝

```
b = JSON.parse( JSON.stringify(a) )
```
- 局限性 1.无法复制函数  2.原型链没了,对象就是object