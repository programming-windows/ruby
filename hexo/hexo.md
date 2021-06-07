# Employ HexO to Generate Your Website

[^_^]:
https://www.cnblogs.com/visugar/p/6821777.html

* [hexo���½�ҳ������ηŶ�����£�](https://www.zhihu.com/question/33324071)
* [���䣺hexo+next���⼰���߹��Ŀ�](https://blog.csdn.net/weixin_42608550/article/details/87876529)
* [Github+Hexoʹ��NexT������Ż�](https://www.jianshu.com/p/67b731c3f840?utm_campaign=maleskine&utm_content=note&utm_medium=seo_notes&utm_source=recommendation)
* [Next����(Hexo)](https://www.jianshu.com/p/5d5931289c09)
* [Github Page+Hexo](https://blog.csdn.net/weixin_43738731/article/details/85843474?utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control)
* [hexo-theme-next](https://github.com/theme-next/hexo-theme-next)

*************************

���˰���ʱ������� HexO �İ�װ�������ܽ�һ���������Ŀӹ��պ�װ�ο���

## 1 �ؼ��Ŀӣ����� Node.js

�����Ŀ��Ȳ�˵�ˣ����Ŀ��ǵ����һ������ʱ
```PowerShell
hexo generate
```
ʱ������Ϊ��֪�����������������ΰ������϶��ַ����������ɹ���
����������׼������ʱ������������ Linux ��װʱҲ���������ƴ���
<https://stackoverflow.com/questions/67516168/i-just-installed-hexo-static-site-generator-on-debian-and-ran-hexo-server-to-see>
˵���Ǵ��������ԭ�����£�

>Function String.matchAll() is supported in Node.js from version 12.0.0, so, 
upgrade your nodejs to a version greater than 12.0.0.

���뵽�ҵ� Node.js �ǰ�װ Visual Studio Enterprise 2017 ʱѡװ��ȥ�ģ�
ʱ���Ѿ���Զ����û�и��¹�������Ҳ����������ǣ�

```PowerShell
node -v
```
�����ʾ�汾���� v10.16.0��������µ����°汾�����º���Ȼ���������ֽ��͵��ȶ��汾��
�ֹ����Ļ����������ǲ��У��汾������ʾ v10.16.0��

cmd ���ҵ� path (PowerShell ��ʶ�� path �����û�뵽��)��
Ҳ������ cmd ��ʹ������ where node �ҳ���װ·����PowerShell �¿���ʶ������û���������
���� Node �İ�װ·��Ϊ D:\Program Files\nodejs��
���׼�����°汾�� node ��������λ�ã�**�Ļ�������û�ã�**����
�Ƚ� nodejs �ļ��и���Ϊ nodejs_10_16_0����ֹʧ�ܺ��޷��˻أ���
���� node-v12.22.1-win-x64.zip ���ѹ�� D:\Program Files\ ��������Ϊ nodejs��
��������������

```PowerShell
node -v
```
�����ʾ�汾���� v12.22.1!

```PowerShell
hexo generate
```
��ɹ���


## 2 ��ϸ�İ�װ����

```PowerShell
npm i -g hexo
```
�����������һ��Ŀ¼ C:\Users\jiche\AppData\Roaming\npm\node_modules\hexo

��װ���鿴����װ�İ汾:
```PowerShell
hexo -v
```

ʹ�� hexo ��ʼ����վĿ¼:
```PowerShell
hexo init
```
ע�������Ŀ¼�ǿգ���ʼ�����ܻ�ʧ�ܣ���ʱ��Ҫ��һ����Ŀ¼����ʼ����
C:\Users\jiche\AppData\Roaming\npm\node_modules\hexo �������Ҳ���ܳ���
���ӵ� github �����粻������ܳ���
Ȼ�󽫳�ʼ���õ����ݿ��������Լ���վ����Ŀ¼�С�

**ע��Ҫ��init��õ���.gitignore�����Լ��Ľ��кϲ���**

�޸� _config.yml �ļ���һЩ����(ð��֮������һ����ǿո��)��
```yml
deploy:
  type: git
  repo: https://github.com/YourgithubName/YourgithubName.github.io.git
  branch: master
```

�ڱ� hexo ��ʼ������Ŀ¼�а�װ hexo-server:
```PowerShell
npm i hexo-server
```

�ٽ������ blog Ŀ¼���ֱ�ִ���������
```PowerShell
hexo clean
hexo generate
hexo server
```

����������룺http://localhost:4000
�Ϳ��Կ�������ˡ�

## 3 �޸ļ���������

hexo��ʼ��֮��Ĭ�ϵ�������landscape , 
����[ȥ�����ַ����ѡ����Ҫ������](https://hexo.io/themes/)��
�� github �������������ƻᷢ�ָ������ʹ�ý��ܡ�

δ��μ���

<https://www.cnblogs.com/visugar/p/6821777.html> ��



