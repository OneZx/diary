> 最简单的深拷贝

```
b = JSON.parse( JSON.stringify(a) )
```
- 局限性 无法复制函数 原型链没了