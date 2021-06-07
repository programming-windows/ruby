# Employ HexO to Generate Your Website

[^_^]:
https://www.cnblogs.com/visugar/p/6821777.html

* [hexo下新建页面下如何放多个文章？](https://www.zhihu.com/question/33324071)
* [绝配：hexo+next主题及我走过的坑](https://blog.csdn.net/weixin_42608550/article/details/87876529)
* [Github+Hexo使用NexT主题和优化](https://www.jianshu.com/p/67b731c3f840?utm_campaign=maleskine&utm_content=note&utm_medium=seo_notes&utm_source=recommendation)
* [Next主题(Hexo)](https://www.jianshu.com/p/5d5931289c09)
* [Github Page+Hexo](https://blog.csdn.net/weixin_43738731/article/details/85843474?utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control)
* [hexo-theme-next](https://github.com/theme-next/hexo-theme-next)

*************************

花了半天时间完成了 HexO 的安装，这里总结一下所遇到的坑供日后安装参考。

## 1 关键的坑：升级 Node.js

其它的坑先不说了，最大的坑是到最后一步生成时
```PowerShell
hexo generate
```
时出错。因为不知道问题在哪里，反复多次按照网上多种方法处理都不成功。
几乎都绝望准备放弃时，发现有人在 Linux 安装时也出现了类似错误
<https://stackoverflow.com/questions/67516168/i-just-installed-hexo-static-site-generator-on-debian-and-ran-hexo-server-to-see>
说的是错误产生的原因如下：

>Function String.matchAll() is supported in Node.js from version 12.0.0, so, 
upgrade your nodejs to a version greater than 12.0.0.

联想到我的 Node.js 是安装 Visual Studio Enterprise 2017 时选装上去的，
时间已经久远而且没有更新过，怀疑也因此引起。如是：

```PowerShell
node -v
```
结果显示版本号是 v10.16.0。必须更新到最新版本。更新后依然出错，于是又降低到稳定版本。
手工更改环境变量后还是不行，版本号总显示 v10.16.0。

cmd 下找到 path (PowerShell 不识别 path 命令，真没想到！)，
也可以在 cmd 上使用命令 where node 找出安装路径（PowerShell 下可以识别该命令但没有输出），
发现 Node 的安装路径为 D:\Program Files\nodejs，
因此准备将新版本的 node 拷贝到该位置（**改环境变量没用！**）。
先将 nodejs 文件夹改名为 nodejs_10_16_0（防止失败后无法退回），
下载 node-v12.22.1-win-x64.zip 后解压到 D:\Program Files\ 再重命名为 nodejs。
完成上述步骤后再

```PowerShell
node -v
```
结果显示版本号是 v12.22.1!

```PowerShell
hexo generate
```
后成功！


## 2 详细的安装步骤

```PowerShell
npm i -g hexo
```
结束后会增加一个目录 C:\Users\jiche\AppData\Roaming\npm\node_modules\hexo

安装完后查看所安装的版本:
```PowerShell
hexo -v
```

使用 hexo 初始化网站目录:
```PowerShell
hexo init
```
注意如果该目录非空，初始化可能会失败，此时需要建一个空目录来初始化，
C:\Users\jiche\AppData\Roaming\npm\node_modules\hexo 如果不空也可能出错，
连接到 github 的网络不好亦可能出错。
然后将初始化好的内容拷贝进你自己网站开发目录中。

**注意要把init后得到的.gitignore与你自己的进行合并！**

修改 _config.yml 文件的一些配置(冒号之后都是有一个半角空格的)：
```yml
deploy:
  type: git
  repo: https://github.com/YourgithubName/YourgithubName.github.io.git
  branch: master
```

在被 hexo 初始化过的目录中安装 hexo-server:
```PowerShell
npm i hexo-server
```

再进入你的 blog 目录，分别执行以下命令：
```PowerShell
hexo clean
hexo generate
hexo server
```

打开浏览器输入：http://localhost:4000
就可以看到结果了。

## 3 修改及配置主题

hexo初始化之后默认的主题是landscape , 
可以[去这个地址里面选择想要的主题](https://hexo.io/themes/)。
在 github 中搜索主题名称会发现该主题的使用介绍。

未完参见：

<https://www.cnblogs.com/visugar/p/6821777.html> 后部



