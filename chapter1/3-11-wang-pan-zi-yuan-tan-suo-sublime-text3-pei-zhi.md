#### 3-11-1 资源搜索

- [云盘精灵](https://www.yunpanjingling.com/)
- 希望上面这个好东东过些时间仍然可以用，希望不被和谐~~搜集一些编程视频真的是利器呀~

#### 3-11-2 Sublime Text3插件安装
- 打开sublime 按** Ctrl + ` **调出console
- 粘贴以下代码到命令行并回车（可能会卡一会儿，请等待）

```
import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```
---

![](/assets/3-11-sublime.png)

- 重启Sublime Text 3
- 在Preferences中看到如下图所示出现，表示安装成功

![](/assets/3-11-control.png)

> 用package control安装插件方法：

- 1. 按`Ctrl+Shift+P` 调出命令面板
- 2. 输入`install package` 选中回车
- 3. 在弹出的窗口中输入要安装的插件

![](/assets/3-11-install.png)

> Sublime text3插件推荐

- 1. Emmet 一种快速编写html/css的方法