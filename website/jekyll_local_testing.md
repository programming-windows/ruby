# Testing your GitHub Pages site locally with Jekyll

<https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll>

****************************************

You can build your GitHub Pages site locally to preview and test changes to your site.

Anyone with read permissions for a repository can test a GitHub Pages site locally.

## 0 TRAPs

### 0.1 Change gem source

在大中华，由于 rubygems.org 无法访问，你需要更换 gem source。命令如下：
```shell
$ gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
$ gem sources -l
https://gems.ruby-china.com
# 确保只有 gems.ruby-china.com
```

### 0.2 Generate Gemfile

在后面运行 `bundle install` 之前，必须先生成 `Gemfile`。
如何生成参见：[Gemfile](../ruby/gemfile.md#如何生成-Gemfile) 。

### 0.3 同步更新
为了保证本地 PC 上的代码管理工具都能够与 `GitHub Pages` 保持同步更新，
只需要运行代码 `bundle update github-pages` 或者 `bundle update` 即可。

Please also see [3 Updating the GitHub Pages gem](#updating-the-gitHub-pages-gem)

## 1 Prerequisites

Before you can use Jekyll to test a site, you must:

* Install [Jekyll](https://jekyllrb.com/docs/installation/).
* Create a Jekyll site. For more information, see "[Creating a GitHub Pages site with Jekyll](https://docs.github.com/en/articles/creating-a-github-pages-site-with-jekyll)."

We recommend using [Bundler](http://bundler.io/) to install and run Jekyll. Bundler manages 
Ruby gem dependencies, reduces Jekyll build errors, and prevents environment-related bugs. 
To install Bundler:

1. Install Ruby. For more information, see "[Installing Ruby](https://www.ruby-lang.org/en/documentation/installation/)" 
in the Ruby documentation.
2. Install Bundler. For more information, see "[Bundler](https://bundler.io/)."

## 2 Building your site locally

1. Open Git Bash.
2. Navigate to the publishing source for your site. For more information about publishing sources, 
see "[About GitHub Pages](https://docs.github.com/en/articles/about-github-pages#publishing-sources-for-github-pages-sites)."
3. Run bundle install.
4. Run your Jekyll site locally.
```shell
    $ bundle exec jekyll serve
    > Configuration file: /Users/octocat/my-site/_config.yml
    >            Source: /Users/octocat/my-site
    >       Destination: /Users/octocat/my-site/_site
    > Incremental build: disabled. Enable with --incremental
    >      Generating...
    >                    done in 0.309 seconds.
    > Auto-regeneration: enabled for '/Users/octocat/my-site'
    > Configuration file: /Users/octocat/my-site/_config.yml
    >    Server address: http://127.0.0.1:4000/
    >  Server running... press ctrl-c to stop.
```
5. To preview your site, in your web browser, navigate to `http://localhost:4000`.

## 3 Updating the GitHub Pages gem

Jekyll is an active open source project that is updated frequently. If the `github-pages` gem 
on your computer is out of date with the `github-pages` gem on the GitHub Pages server, your 
site may look different when built locally than when published on GitHub. To avoid this, 
**regularly update** the `github-pages gem` on your computer.

1. Open Git Bash.
2. Update the `github-pages` gem.
    * If you installed Bundler, run `bundle update github-pages`.
    * If you don't have Bundler installed, run `gem update github-pages`.



