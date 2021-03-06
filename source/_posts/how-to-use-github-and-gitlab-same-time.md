---
title: mac电脑上同时使用多个git平台
toc: true
comment: true
date: 2017-07-07 16:05:48
categories: Software
tags: git
---



用ssh的方式使用git平台的时候，需要先预先生成秘钥，在git平台设置了公钥，才可以使用

我们可以同时使用了多个git平台，如github和gitlab

只需要为他们生成不同的秘钥就可以了


<!--more-->

## 生成秘钥，指定秘钥的名称

```
//生成gitlab的秘钥
ssh-keygen -t rsa -f ~/.ssh/id_rsa.gitlab -C "test_aaa@126.com"


//生成github的秘钥
ssh-keygen -t rsa -f ~/.ssh/id_rsa.github -C "test_bbb@126.com"
```

执行完上述的操作的时候，在`~/.ssh`目录就可以看到如下的4个文件

```
id_rsa.gitlab        gitlab的私钥
id_rsa.gitlab.pub    gitlab的公钥
id_rsa.github        github的私钥
id_rsa.github.pub    github的公钥
```


## 将私钥添加到 ssh-agent 中
```
ssh-add id_rsa.gitlab
ssh-add id_rsa.github
```
这种添加是临时性的，重启之后需要再次添加，解决方法见[解决重启后私钥失效的问题](https://16bh.github.io/2017/07/07/fix-invalid-private-key-after-reboot/)

## 将公钥添加到git平台中

以github为例，在`Personal settings/SSH and GPG keys`中就可以添加`ssh key`了，如下图所示

![20170707149941538098409.png](how-to-use-github-and-gitlab-same-time/20170707149941538098409.png)


## 测试ssh

执行下面的命令测试ssh

```
ssh -T git@github.com
```

若出现类似下面的提示，说明ssh可用

![201707071499415537639.png](how-to-use-github-and-gitlab-same-time/201707071499415537639.png)

然后就可以使用ssh的方式使用git平台了

