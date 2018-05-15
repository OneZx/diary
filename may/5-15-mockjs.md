> Node安装

- `npm install mockjs`

```
// 使用 Mock
var Mock = require('mockjs')
var data = Mock.mock({
    // 属性 list 的值是一个数组，其中含有 1 到 10 个元素
    'list|1-10': [{
        // 属性 id 是一个自增数，起始值为 1，每次增 1
        'id|+1': 1
    }]
})
// 输出结果
console.log(JSON.stringify(data, null, 4))
```

#####语法
- [mock-github](https://github.com/nuysoft/Mock/wiki/Syntax-Specification)
- [mock-segmentfault](https://segmentfault.com/a/1190000008839142)

####数据模板格式
```
'name|rule':value
属性名|生成规则:属性值

//生成规则有7种格式
'name|min-max': value
'name|count': value
'name|min-max.dmin-dmax': value
'name|min-max.dcount': value
'name|count.dmin-dmax': value
'name|count.dcount': value
'name|+step': value
// 生成规则的含义需要依赖属性值的类型才能确定
// 属性值中可以含有@占位符
```

##### 1.属性值是字符串string
- `'name|min-max': string`

通过重复`string`生成一个字符串,重复次数大于等于min,小于等于max

- `'name|count': string`

重复string次数等于`count`

##### 2.属性值是Number
- 'name|+1:number'
属性值自动加1,初始值为number

- 'name|min-max':number
生成一个大于等于min,小鱼等于max的整数,属性值number用来确定类型