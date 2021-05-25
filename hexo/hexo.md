# HexO

[^_^]:
https://www.cnblogs.com/visugar/p/6821777.html

*************************

安装:
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
然后将初始化好的内容拷贝进来。

在被 hexo 初始化过的目录中安装 hexo-server:
```PowerShell
npm i hexo-server
```

