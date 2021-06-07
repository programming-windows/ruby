# Jekyll

* [Github+Jekyll 搭建个人网站详细教程](https://www.jianshu.com/p/9f71e260925d)
* [GitHub Pages + Jekyll 搭建网站、更换主题](https://www.jianshu.com/p/da1287bc7874)
* [GithubPages+Jekyll搭建个性化主题博客](https://blog.csdn.net/sinat_34439107/article/details/78443957)
* [pages-themes leap-day](https://github.com/pages-themes/leap-day)
* [jekyll 安装遇到的问题](https://www.jianshu.com/p/219f62c736f7)
* [2020-01-02 Jekyll Theme各种问题大集合](https://www.jianshu.com/p/5425e77263ac)
* [6 reasons to blog in Markdown with Jekyll](https://opensource.com/life/16/2/my-jekyll-workflow)
* [http://jekyllcn.com/docs/usage/](http://jekyllcn.com/docs/usage/)
* [Building a self-updating profile README for GitHub](https://simonwillison.net/2020/Jul/10/self-updating-profile-readme/)
* [Jekyll + Github Pages 博客搭建入门](https://www.jianshu.com/p/9f198d5779e6)
* [Jekyll安装教程](https://www.jianshu.com/p/1093b5565918)
* [不要在master分支上部署pages服务](https://www.zhihu.com/question/317491354/answer/632985629)

*****************

1. 内容分支 content
2. 呈现分支 master
3. 多个 theme 分支

## 0 重要命令

1. 清除旧版 Ruby
```yml
yum remove ruby
```
若为源码，使用如下命令
```cmake
cd <your-ruby-source-path>
make uninstall
```



## 1 安装 Jekyll

### 1.1 Steps

1. 下载安装 [Ruby installer](https://rubyinstaller.org/downloads/) x64 版本 2.7.3-1

2. 下载 [RubyGems](https://rubygems.org/pages/download) 到 F:\\ruby\\RubyGems
并解压，完成后进入相应目录并 ruby 运行 setup.rb：
```shell
cd F:\ruby\RubyGems\rubygems-3.2.17
ruby setup.rb
```

3. 在 PowerShell 中执行 gem install jekyll

4. 用jekyll命令创建一个博客模板,打开命令行执行：
```ruby
jekyll new testblog
cd testblog
jekyll server
```

5. 在浏览器中输入 http://127.0.0.1:4000/ 可浏览所创建的网页

### 1.1 Directory structure of Jekyll

jekyll目录结构主要包含如下目录：

> _posts 博客内容
> 
> _pages 其他需要生成的网页，如About页
> 
> _layouts 网页排版模板
> 
> _includes 被模板包含的HTML片段，可在_config.yml中修改位置
> 
> assets 辅助资源 css布局 js脚本 图片等
> 
> _data 动态数据
> 
> _sites 最终生成的静态网页
> 
> _config.yml 网站的一些配置信息
> 
> index.html 网站的入口

那么这些目录是如何运作的呢？

1. 我们打开根目录下的index.html可以看到：
```html
—
layout: home-page
—
html代码段
```

## 2 Jekyll 主题选择

我们先选择 github pages 提供的 The Leap day theme 来完成一个初步的构建，后续再做细致地探讨。

### 2.1 The Leap day theme

参见 [The Leap day theme](https://github.com/pages-themes/leap-day)

#### 2.1.1 Usage

To use the Leap day theme:

1. Add the following to your site's `_config.yml`:

    ```yml
    theme: jekyll-theme-leap-day
    ```

2. Optionally, if you'd like to preview your site on your computer, add the following to your site's `Gemfile`:

    ```ruby
    gem "github-pages", group: :jekyll_plugins
    ```

```ruby
$ jekyll build
# => 当前文件夹中的内容将会生成到 ./_site 文件夹中。

$ jekyll build --destination <destination>
# => 当前文件夹中的内容将会生成到目标文件夹<destination>中。

$ jekyll build --source <source> --destination <destination>
# => 指定源文件夹<source>中的内容将会生成到目标文件夹<destination>中。

$ jekyll build --watch
# => 当前文件夹中的内容将会生成到 ./_site 文件夹中，
#    查看改变，并且自动再生成。
```


