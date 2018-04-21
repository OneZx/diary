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