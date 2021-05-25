# Employ HexO to Generate Your Website

[^_^]:
https://www.cnblogs.com/visugar/p/6821777.html

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



