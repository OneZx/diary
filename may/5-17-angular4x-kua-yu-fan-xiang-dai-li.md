- 新建一个JSON文件,名为`proxy.config.json`

```
{
  "/api":{
    "target":"http://localhost:8100/" // 指向需要代理的ip
  }
}
```

- 配置`package.json`文件中`"start"`

```
"scripts": {
  "ng": "ng",
  "start": "ng serve  --proxy-config proxy.config.json",
  "build": "ng build  --prod --aot",
  "test": "ng test",
  "lint": "ng lint",
  "e2e": "ng e2e"
}
```