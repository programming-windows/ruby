# Testing your GitHub Pages site locally with Jekyll

<https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll>

****************************************

You can build your GitHub Pages site locally to preview and test changes to your site.

Anyone with read permissions for a repository can test a GitHub Pages site locally.

## 0 TRAPs

### 0.1 Change gem source

�ڴ��л������� rubygems.org �޷����ʣ�����Ҫ���� gem source���������£�
```shell
$ gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
$ gem sources -l
https://gems.ruby-china.com
# ȷ��ֻ�� gems.ruby-china.com
```

### 0.2 Generate Gemfile

�ں������� `bundle install` ֮ǰ������������ `Gemfile`��
������ɲμ���[Gemfile](../ruby/gemfile.md#�������-Gemfile) ��

### 0.3 ͬ������
Ϊ�˱�֤���� PC �ϵĴ�������߶��ܹ��� `GitHub Pages` ����ͬ�����£�
ֻ��Ҫ���д��� `bundle update github-pages` ���� `bundle update` ���ɡ�

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



