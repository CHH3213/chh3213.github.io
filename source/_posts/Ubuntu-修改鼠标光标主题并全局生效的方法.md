---
title: Ubuntu 修改鼠标光标主题并全局生效的方法
top: false
cover: http://api.mtyqx.cn/tapi/random.php?1513231265465
coverWidth: 1200
coverHeight: 750
toc: true
mathjax: true
coments: true
date: 2022-12-03 20:03:13
tags:
category:
---

一般情况下，ubuntu默认的鼠标光标主题都比较不好看，所以我们可以通过以下方法进行修改。
<!--more-->


## 获取鼠标光标主题

在[网站](https://www.gnome-look.org/browse?cat=107&ord=latest)选择你想要的鼠标主题，例如我选择的是[这一款](https://www.gnome-look.org/s/Gnome/p/1360254/)。

![在这里插入图片描述](https://img-blog.csdnimg.cn/a25d23933da9417b9f806fa6e34efa94.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/0e6a926ecfdf4c56bfb9a6061fb75fde.png)
点击下载后，将压缩包解压，并进入该文件夹内，将文件夹移至`/usr/share/icons`目录内

```bash
sudo mv oreo_spark_pink_cursors /usr/share/icons
```

## 配置主题

打开ubuntu系统左下角的查找应用程序，输入`tweak`，打开出现的应用（中文系统下是`优化`，英文系统是`tweak`）。
![在这里插入图片描述](https://img-blog.csdnimg.cn/db6d8fec0fde4743b8947582997b0fde.png)
在`优化`中选择`外观`，找到`光标`，选择你想安装的鼠标主题即可。

![在这里插入图片描述](https://img-blog.csdnimg.cn/35e08399c6944c248e978c8aa04fb7d0.png)

## 将下载的鼠标光标主题加入到 alternative x-cursor-theme

在进行步骤2后，虽然鼠标主题生效了，但是并没有全局生效，在一些应用内依旧是原来的主题。所以，还需要进行以下步骤的配置。

打开终端，在终端输入以下命令，将鼠标光标主题加入到 `alternative x-cursor-theme` 中

```bash
sudo update-alternatives --install /usr/share/icons/default/index.theme x-cursor-theme /usr/share/icons/你的鼠标光标主题名称/cursor.theme 20
```

例如，我的是

```bash
sudo update-alternatives --install /usr/share/icons/default/index.theme x-cursor-theme /usr/share/icons/oreo_spark_pink_cursors/cursor.theme 20
```

接着，在终端输入以下命令：

```bash
sudo update-alternatives --config x-cursor-theme
```

选择你的候选项编号

![在这里插入图片描述](https://img-blog.csdnimg.cn/2997c8b3c1ef4055a67023218c6ad4b5.png)

选择完成后，重启系统生效。

## 参考资料

- [https://vincentbel.com/ubuntu-change-cursor-theme/](https://vincentbel.com/ubuntu-change-cursor-theme/)
- [https://www.youtube.com/watch?v=U_aQv74bHRQ](https://www.youtube.com/watch?v=U_aQv74bHRQ)
