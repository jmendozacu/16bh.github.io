---
title: 用phpStorm进行magento开发的几个Tips
categories: Software
top: 6
toc: false
comment: true
date: 2017-04-01 16:41:58
tags: [magento,phpstorm]
---



- 安装phpcs
- 安装phpmd
- 安装magicento插件
- 只索引有用的文件夹
- 常用magento代码片段


<!--more-->

> 参考：
> https://mirasvit.com/blog/guide-for-setting-up-phpstorm-for-magento-2-developments.html

# 安装phpcs

phpcs可以统一编码的规范，常用的是psr2

[mac下phpStorm配置使用phpcs](https://16bh.github.io/2017/04/01/phpcs-in-phpstorm-on-mac/)



# 安装phpmd

php代码纠错

[mac下phpStorm配置使用phpmd](https://16bh.github.io/2017/04/01/phpmd-in-phpstorm-on-mac/)

# 安装[magicento](http://magicento.com/ )插件
![20170401149103633058337.png](phpstorm-develop-magento-skills/20170401149103633058337.png)

# 只对用的到的文件夹进行索引
```
/bin/
/dev/
/pub/
/setup/
/var/cache/
/var/log/
/var/page_cache
/var/view_processed
```
建议将以上的文件夹标记为`Excluded`，这样就不会浪费phpStorm的性能对它们进行索引了

![20170401149103630080427.png](phpstorm-develop-magento-skills/20170401149103630080427.png)

# 设置常用代码片段

https://16bh.github.io/2017/04/01/phpstorm-live-template/
