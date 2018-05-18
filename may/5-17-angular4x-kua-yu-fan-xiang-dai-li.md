> angular4.x 解决跨域问题(ionic3 直接在ionic.config.json中配置)

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

> ionic3 配置

- ionic.config.json中

```
  "proxies": [
    {
      "path": "/api",
      "proxyUrl": "https://api.instagram.com/api"
    }
  ]
```
在想访问`https://api.instagram.com/api/xxx`的时候,就改成访问`/api/xxx`,ionic会自动把以`http://localhost:8100/api`开头的请求都代理成`https://api.instagram.com/api`访问

```
// myproject
{
  "name": "gphone",
  "app_id": "",
  "type": "ionic-angular",
  "integrations": {
    "cordova": {}
  },
  "proxies": [
    {
      "path": "/",
      "proxyUrl": "https://api.douban.com"
    }
  ]
}


```