# Jekyll

[^_^]:
https://www.jianshu.com/p/9f71e260925d

*****************

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


