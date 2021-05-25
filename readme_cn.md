# 通向 Ruby 编程

For English version please [switch to the English version](readme.md)

[^_^]:
https://www.imooc.com/article/46905

**********************************

Ruby 语言学习备忘录。

Ruby is the support language for static web generator jekyll.
Since there are several popular static website generators, 
[this article](static_website_generator.md#jekyll-vs-hugo-vs-hexo) 
gives a detailed comparison among all the popular ones.

点击转到：[Jekyll vs Hugo vs Hexo](static_website_generator.md#jekyll-vs-hugo-vs-hexo)

Hexo 的安装过程请参见本站的文章： 
["Employ HexO to Generate Your Website"](hexo/hexo.md).

## 1 引言

在 Windows 上编译 Ruby 一直是一件要命的事情，虽然官方提供了Ruby Installer，
但是从Ruby 1.9开始，Ruby Installer就是使用MinGW进行编译了，一般使用的话问题不大，
但是如果你想要把Ruby解释器集成到自己的C/C++应用程序里面做深度开发的话，
那么就意味着你必须要使用gcc作为后端（Ruby Installer只提供.a格式的lib库文件），
那么也就意味着你可以和Visual Studio这个宇宙第一IDE说再见了……

我自己就有如上需求，主要是想要把 Ruby 嵌入游戏引擎中做脚本层（类似于其他引擎使用Lua、
Python这种应用场景），所以折腾了很久。虽说Ruby一直都提供了win32的编译configure，
但是在早期版本的VC的编译器下简直形同虚设，要么缺这个依赖要么缺那个依赖，
总之就是完全编译不起来，令人窒息。

Visual Studio 2017之后情况开始好转，于是我尝试使用Visual Studio 2017进行Ruby的编译，
虽然过程中也踩了些坑，但还是相对顺利地完成了编译，并且成功集成到了C++之中，
下面就对整个过程做个总结。

## 2 准备

安装Visual Studio Community 2019。

编译 Ruby 最基本的自然是它的源码，
可以从[Ruby官网上](https://www.ruby-lang.org/en/downloads/)下载，
截至目前（2021年5月24日），latest stable release的Ruby版本号为3.0.1，
但由于该版本去掉了 webrick，后续在安装 jekyll 时问题多多（我试了几次均失败，
按网上的办法都未成功）。
因此我下载的就是 x64 的 windows 下 2.7.3-1 版本的 Ruby，
文件名 rubyinstaller-devkit-2.7.3-1-x64.exe。

下载下来文件名为ruby-2.5.0.tar.gz，解压出来，这里假设源代码的目录为：D:\ruby，我们要安装到D:\ruby-bin中。

除了Ruby源代码之外，Ruby的编译还依赖于一些第三方扩展，比如dbm、gdbm、readline、openssl、zlib之类的，这些扩展你可用可不用，如果要用到的话就需要去编译，如果不用的话就不管它（如果不编译不用的扩展的话，在编译Ruby的时候就会提示你某某扩展将不会被安装，这个时候不要惊慌不要害怕，统统无视掉就行了 _(:з」∠)_）。这里我选择了openssl和zlib作为依赖进行编译。

. 首先去openssl官网上下载源码，我下载的是openssl-1.0.2n.tar.gz,，下载下来后本地解压，这里假设目录为：D:\openssl，为了编译openss，我们还需要安装Perl环境，这里简单地安装ActivePerl就行了（体积有点大）；此外，还需要去nasm官网上下载nasm汇编器，我这里下载的是http://www.nasm.us/pub/nasm/releasebuilds/2.13.03/win64/nasm-2.13.03-installer-x64.exe，简单安装完即可，这里假设安装目录为D:\nasm。

然后去zlib官网上下载源码，我下载的是zlib-1.2.11.tar.gz，同样地，下载下来后本地解压，这里假设目录为：D:\zlib。

继续新建一个文件夹如D:\Dependency，然后在里面新建三个文件夹：D:\Dependency\bin、D:\Dependency\include、D:\Dependency\lib，之后我们编译好的依赖相关文件会分别放进这3个文件夹里面。

最后，在控制面板中打开系统和安全 -> 高级设置 -> 环境变量，然后在Path中添加D:\Dependency\bin以及D:\nasm，再新建一个INCLUDE，设定为D:\Dependency\include，最后再新建一个LIB然后设定为D:\Dependency\lib，这样一来，-上面2个依赖编译好的相关文件，在Ruby编译的时候就能够被找到了。

以上就是编译Ruby前所有准备工作。







