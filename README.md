# Hexo���ʹ�̳�

## ׼������

* ��װgit
* ��װNode.js
* ע��github�˺�
* �����µĲֿ⣬����Ϊ`xx.github.io`
* ��ӱ��ص�����֤

```
ssh-keygen -t rsa -C "Github��ע�������ַ"
```
���������ļ���id_rsa/id_rsa.pub������id_rsa.pub������ݵ�github��ssh��֤key�м���

## ��װhexo

* �������й���

```
npm install -g hexo-cli
```

* ��ʼ����Ŀ

```
hexo init <folder>
```

* ���ļ�����ִ��

```
npm install
```

* ��װnext����

```
mkdir themes/next
curl -s https://api.github.com/repos/iissnan/hexo-theme-next/releases/latest | grep tarball_url | cut -d '"' -f 4 | wget -i - -O- | tar -zx -C themes/next --strip-components=1
```

> ����װ���ˣ�����ֱ�ӿ�¡next��Ŀ����

```
git clone https://github.com/iissnan/hexo-theme-next themes/next
```

## ��������

```
title: ��������_SN
subtitle: ������Ϊ��Ϊ���ճɣ�����֮������ʲô��һ���첻������ 
description: Painting talent persisted in playing music, but also dreamed of becoming a director and finally becoming a programmer's great artist.
author: chenshinan
language: zh-Hans
timezone: Asia/Shanghai

url: http://chenshinan.github.io
theme: next
deploy:
  type: git
  repository: git@github.com:chenshinan/chenshinan.github.io.git
  branch: master
```

## ��������

* ��װgit����ű�

```
npm install hexo-deployer-git --save
```

* ����ҳ��

```
hexo new page categories 
```
��������ҳ�棬��source/categories/index.md�����type����
```
---
title: ���·���
date: 2018-01-01 10:00:00
type: "categories"   #�ⲿ��������ӵ�
---
```
��ģ���������������ԣ�֮�󴴽��������¶�������������
```
title: {{ title }}
date: {{ date }}
categories:
tags:
```

* ��������

```
hexo new posts "Java8ѧϰ�ʼ�" //hexo n "xx"
```
������һ��markdown`./source/_posts/Java8ѧϰ�ʼ�.md`

* ���ɾ�̬ҳ��

```
hexo clean
hexo generate //hexo g
```

* ������������

```
hexo deploy //hexo d
```

* ��������

```
hexo server //hexo s
```
������������Ĭ������£�������վΪhttp://localhost:4000/

�ο����ף�

- [�ٷ��ĵ�](https://hexo.io/zh-cn/docs/)
- [github hexo�����ȫ](https://github.com/hexojs/hexo/wiki/Themes)
- [hexo+next���⼰���߹��Ŀ�](https://www.jianshu.com/p/21c94eb7bcd1)