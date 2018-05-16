> [typescript](http://www.typescriptlang.org/)

[typescript-playground](http://www.typescriptlang.org/play/index.html)

##### typescript字符串特性
- 多行字符串

```
//ts
let content = `aaa
bbb
ccc`

// js
var content = "aaa\nbbb\nccc";
```

- 字符串模板

```
var name = 'doyou';
var getName = ()=> 'doyou';
console.log(`hello ${name}`);
console.log(`hello ${getName()}`);

//js
var name = 'doyou';
var getName = function () { return 'doyou'; };
console.log("hello " + name);
console.log("hello " + getName());

```
- 自动拆分字符串

当在用一个字符串模板去调用一个方法的时候，这个字符串模板里面表达式的值会自动赋给被调用方法中的参数
```
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
```