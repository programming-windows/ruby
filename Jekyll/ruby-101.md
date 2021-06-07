# Ruby 101

[Ruby 101 for Jekyll](https://jekyllrb.com/docs/ruby-101/)

[Download Ruby](https://www.ruby-lang.org/en/downloads/)

[The easy way to install Ruby on Windows](https://rubyinstaller.org/)

[用Visual Studio 2017编译Ruby 2.5.0并集成在C++中](https://www.imooc.com/article/46905)

[Ruby China](https://ruby-china.org/)

[windows下安装ruby和 rails的痛苦经历](https://www.cnblogs.com/51kata/p/5469722.html)

[Ruby 开发人员中心](https://azure.microsoft.com/zh-cn/develop/ruby/)

*******************


<span id = "TopPermalink"></span>


Jekyll is written in Ruby. If you’re new to Ruby, this page helps you learn some of the terminology.

[Gems](https://jekyllrb.com/docs/ruby-101/#gems)

Gems are code you can include in Ruby projects. Gems package specific functionality. You can share gems across multiple projects or with other people. Gems can perform actions like:

* Converting a Ruby object to JSON
* Pagination
* Interacting with APIs such as GitHub

Jekyll is a gem. Many Jekyll plugins are also gems, including jekyll-feed, jekyll-seo-tag and jekyll-archives.

[Gemfile](https://jekyllrb.com/docs/ruby-101/#gemfile)

A `Gemfile` is a list of gems used by your site. Every Jekyll site has a Gemfile in the main folder.

For a simple Jekyll site it might look something like this:

```ruby
source "https://rubygems.org"

gem "jekyll"

group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-seo-tag"
end
```

## Bundler

[go to the top](#TopPermalink)

Bundler is a gem that installs all gems in your Gemfile.

While you don’t have to use Gemfile and bundler, it is highly recommended as it ensures you’re running the same version of Jekyll and its plugins across different environments.

Install Bundler using gem install bundler. You only need to install it once, not every time you create a new Jekyll project.

To install gems in your Gemfile using Bundler, run the following in the directory that has the Gemfile:


