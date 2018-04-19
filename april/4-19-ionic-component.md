> ionic组件

- 新建组件 ionic g component [name]
- app.module.ts中引入

```
// 引入自定义components模块
import { ComponentsModule } from '../components/components.module';
```
- 在需要用的地方直接使用 `<line-tips></line-tips>`