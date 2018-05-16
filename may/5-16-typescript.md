> [typescript](http://www.typescriptlang.org/)

[typescript-playground](http://www.typescriptlang.org/play/index.html)

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
