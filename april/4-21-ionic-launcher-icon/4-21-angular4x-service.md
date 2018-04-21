> 创建服务

- `ng g service my-new-service`

> 引入服务app.module.ts

```
import { StorageService } from './services/storage.service';

/*定义的服务*/
providers: [StorageService],
```
- 其他组件用的时候也要引入

```
import { StorageService } from '../../services/storage.service';
.

```

> 依赖注入服务

```
public storage = new StorageService(); // 可以引入和使用服务, 但官方不推荐这样的方法
  // private storage: StorageService 表示依赖注入服务
constructor(private storage: StorageService) {
  console.log(this.storage);
  this.storage.setItem('username', 'lalala');
}
```