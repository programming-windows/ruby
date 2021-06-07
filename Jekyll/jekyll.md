# Jekyll

* [Github+Jekyll �������վ��ϸ�̳�](https://www.jianshu.com/p/9f71e260925d)
* [GitHub Pages + Jekyll ���վ����������](https://www.jianshu.com/p/da1287bc7874)
* [GithubPages+Jekyll����Ի����ⲩ��](https://blog.csdn.net/sinat_34439107/article/details/78443957)
* [pages-themes leap-day](https://github.com/pages-themes/leap-day)
* [jekyll ��װ����������](https://www.jianshu.com/p/219f62c736f7)
* [2020-01-02 Jekyll Theme��������󼯺�](https://www.jianshu.com/p/5425e77263ac)
* [6 reasons to blog in Markdown with Jekyll](https://opensource.com/life/16/2/my-jekyll-workflow)
* [http://jekyllcn.com/docs/usage/](http://jekyllcn.com/docs/usage/)
* [Building a self-updating profile README for GitHub](https://simonwillison.net/2020/Jul/10/self-updating-profile-readme/)
* [Jekyll + Github Pages ���ʹ����](https://www.jianshu.com/p/9f198d5779e6)
* [Jekyll��װ�̳�](https://www.jianshu.com/p/1093b5565918)
* [��Ҫ��master��֧�ϲ���pages����](https://www.zhihu.com/question/317491354/answer/632985629)

*****************

1. ���ݷ�֧ content
2. ���ַ�֧ master
3. ��� theme ��֧

## 0 ��Ҫ����

1. ����ɰ� Ruby
```yml
yum remove ruby
```
��ΪԴ�룬ʹ����������
```cmake
cd <your-ruby-source-path>
make uninstall
```



## 1 ��װ Jekyll

### 1.1 Steps

1. ���ذ�װ [Ruby installer](https://rubyinstaller.org/downloads/) x64 �汾 2.7.3-1

2. ���� [RubyGems](https://rubygems.org/pages/download) �� F:\\ruby\\RubyGems
����ѹ����ɺ������ӦĿ¼�� ruby ���� setup.rb��
```shell
cd F:\ruby\RubyGems\rubygems-3.2.17
ruby setup.rb
```

3. �� PowerShell ��ִ�� gem install jekyll

4. ��jekyll�����һ������ģ��,��������ִ�У�
```ruby
jekyll new testblog
cd testblog
jekyll server
```

5. ������������� http://127.0.0.1:4000/ ���������������ҳ

### 1.1 Directory structure of Jekyll

jekyllĿ¼�ṹ��Ҫ��������Ŀ¼��

> _posts ��������
> 
> _pages ������Ҫ���ɵ���ҳ����Aboutҳ
> 
> _layouts ��ҳ�Ű�ģ��
> 
> _includes ��ģ�������HTMLƬ�Σ�����_config.yml���޸�λ��
> 
> assets ������Դ css���� js�ű� ͼƬ��
> 
> _data ��̬����
> 
> _sites �������ɵľ�̬��ҳ
> 
> _config.yml ��վ��һЩ������Ϣ
> 
> index.html ��վ�����

��ô��ЩĿ¼������������أ�

1. ���Ǵ򿪸�Ŀ¼�µ�index.html���Կ�����
```html
��
layout: home-page
��
html�����
```

## 2 Jekyll ����ѡ��

������ѡ�� github pages �ṩ�� The Leap day theme �����һ�������Ĺ�������������ϸ�µ�̽�֡�

### 2.1 The Leap day theme

�μ� [The Leap day theme](https://github.com/pages-themes/leap-day)

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
# => ��ǰ�ļ����е����ݽ������ɵ� ./_site �ļ����С�

$ jekyll build --destination <destination>
# => ��ǰ�ļ����е����ݽ������ɵ�Ŀ���ļ���<destination>�С�

$ jekyll build --source <source> --destination <destination>
# => ָ��Դ�ļ���<source>�е����ݽ������ɵ�Ŀ���ļ���<destination>�С�

$ jekyll build --watch
# => ��ǰ�ļ����е����ݽ������ɵ� ./_site �ļ����У�
#    �鿴�ı䣬�����Զ������ɡ�
```


