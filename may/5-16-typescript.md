> [typescript](http://www.typescriptlang.org/)

[typescript-playground](http://www.typescriptlang.org/play/index.html)

##### typescript字符串特性

* 多行字符串

  //ts  
    let content = `aaa  
    bbb  
    ccc`

  // js  
    var content = "aaa\nbbb\nccc";

* 字符串模板

  var name = 'doyou';  
    var getName = \(\)=&gt; 'doyou';  
    console.log\(`hello ${name}`\);  
    console.log\(`hello ${getName()}`\);

  //js  
    var name = 'doyou';  
    var getName = function \(\) { return 'doyou'; };  
    console.log\("hello " + name\);  
    console.log\("hello " + getName\(\)\);

* 自动拆分字符串

当在用一个字符串模板去调用一个方法的时候，这个字符串模板里面表达式的值会自动赋给被调用方法中的参数

    function hello (template, name, age) {
    　　console.log(template);
    　　console.log(name);
    　　console.log(age);
    }
    var myName = "张三";
    var getAge = function () {
    　　return 18;
    }
    hello`Hello, my name's ${myName}, i'm ${getAge()}`;

    //js
    hello(__makeTemplateObject(["Hello, my name's ", ", i'm ", ""], ["Hello, my name's ", ", i'm ", ""]), myName, getAge());

##### 2.ts类型注解

```
let name: string = 'doyou';
let alias: any = 'xixi';
let age: number = 13;
let result: boolean = true;

function test(name: string):string{
    return "";  // string 类型的返回值, void表示无返回值
}
```

##### 3.ts参数新特性

* 参数类型  
    在参数名称后面使用冒号来指定参数的类型

  ```
  let name: string = 'doyou'
  ```

* 默认参数  
    在参数声明后面用等号来指定参数的默认值

```
function print (a: string, b: number, c: boolean = false) {
// 重点：带默认值的参数一定要声明在最后面
　　console.log(a);
　　console.log(b);
　　console.log(c);
}
print("张三", 13, true);　　// 假设三个参数都没有默认值，方法调用时，必须传指定个数的参数，否则 IDE 会提示错误
print("张三", 13);　　// 当第三个参数有默认值的时候，可传，可不传。
```

* 可选参数
    在方法的参数声明后面用问号来标明此参数为可选参数

```
function print(a: string, b?: string, c:boolean = true){
}
// 可选参数必须声明在必选参数后面
```

##### 4.函数新特性

* Rest and Spread\(扩展\)操作符  
    用来声明任意数量的方法参数

  > ES6中的解构赋值

* 对象的解构

```
// ------变量的声明中运用解构
let node = {
    type: "Identifier",
    name: "foo"
};
// 这里的type,name需与对象中的type,name一致
let { type, name } = node;
console.log(type); // "Identifier"
console.log(name); // "foo"

//js
var node = {
    type: "Identifier",
    name: "foo"
};
var type = node.type, name = node.name;
console.log(type); // "Identifier"
console.log(name); // "foo"

//---------变量的赋值解构
let node = {
    type: "Identifier",
    name: "foo"
},
type = "Literal",
name = 5;
// 使用解构来分配不同的值
({ type, name } = node);
console.log(type); // "Identifier"
console.log(name); // "foo"
```

\[注意\]一定要用一对小括号包裹解构赋值语句，JS引擎将一对开放的花括号视为一个代码块。代码块语句不允许出现在赋值语句左侧，添加小括号后可以将块语句转化为一个表达式，从而实现整个解构赋值过程

* 解构赋值表达式\(也就是=右侧的表达式\)

**函数的扩展操作符**
```
求一个数组最大元素 
// ES5 的写法  
Math.max.apply(null, [14, 3, 77])  
// ES6 的写法  
Math.max(...[14, 3, 77])  
//  等同于  
Math.max(14, 3, 77);
```

- **Generator函数**

- [babel中文](https://babeljs.cn/repl/)
```
function* doSomething(){
	console.log("start");
  yield;
  console.log("finish");
}

let fc1 = doSomething();
fc1.next();
fc1.next();
```


