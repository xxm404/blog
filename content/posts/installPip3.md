---
title: "InstallPip3"
date: 2020-10-17T17:09:11+08:00
draft: false
toc: true
images:
tags: 
  - python
---

## 0x0 背景

工作需要，要在`ununtu 14.04.5` 版本上面安装`python3.6` 与`pip3.6` 

## 0x1 安装过程

更新系统软件源`sudo apt-get update`，执行`sudo apt-get install python3.6 -y` 安装成功后，执行`python3 -V`查看

![image-20201017175357727](/Users/xinmian/Library/Application Support/typora-user-images/image-20201017175357727.png)

发现依然是`python3.4`，此处的`python3`是一个软链，删除这个软链，重新创建软链到`python3.6` 

```shell
rm /usr/bin/python3
ln -s /usr/bin/python3.6m /usr/bin/python3
```

此时执行`python3 -V`

![image-20201017175419399](/Users/xinmian/Library/Application Support/typora-user-images/image-20201017175419399.png)

这时执行`pip3 -V`报错

```
Traceback (most recent call last):
  File "/usr/bin/pip3", line 5, in <module>
    from pkg_resources import load_entry_point
  File "/usr/lib/python3/dist-packages/pkg_resources.py", line 1479, in <module>
    register_loader_type(importlib_bootstrap.SourceFileLoader, DefaultProvider)
AttributeError: module 'importlib._bootstrap' has no attribute 'SourceFileLoader'
```

这是因为`pip3`与`python3.6`是通过不同的源安装的，`pip3`是系统默认的`python3.4`携带安装的，陷入僵局

## 0x3 解决方法

需要我们切换到`root`用户下

```shell
sudo su root
```

执行`sudo wget https://bootstrap.pypa.io/ez_setup.py -O - | python3`

执行成功后，切换回原用户，执行`pip3 -V`

![image-20201017180033485](/Users/xinmian/Library/Application Support/typora-user-images/image-20201017180033485.png)

搞定！



### References

> https://ubuntuqa.com/zh-tw/article/8539.html

