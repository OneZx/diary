- CORS(Cross origin resource sharing)跨域资源共享
- [cors-阮一峰](http://www.ruanyifeng.com/blog/2016/04/cors.html)

- Access-Control-Allow-Origin

后端服务器设置`response.setHeader("Access-Control-Allow-Origin", "*");`
- 服务端告诉浏览器,我的服务器接收任何请求来源,请不要拦截
- 后台使用`拦截器统一处理`

```
MultivaluedMap<String, Object> headers = responseContext.getHeaders();

        headers.add("Access-Control-Allow-Origin", "*");
        //headers.add("Access-Control-Allow-Origin", "http://abcd.org"); //allows CORS requests only coming from abcd.org
        headers.add("Access-Control-Allow-Methods", "GET, POST, DELETE, PUT, OPTIONS");
        headers.add("Access-Control-Allow-Headers", "X-Requested-With, Content-Type, X-Codingpedia, Authorization,token");

```

- JSONP只支持`GET`请求

- [RxJS-Chinese-gitbook](https://legacy.gitbook.com/book/buctwbzs/rxjs/details)

- [组件的懒加载 + better](https://www.cnblogs.com/gavin-cn/p/6961376.html)