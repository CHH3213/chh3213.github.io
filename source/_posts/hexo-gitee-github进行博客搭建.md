---
title: hexo+gitee/github进行博客搭建
top: false
cover: http://api.mtyqx.cn/tapi/random.php?
coverWidth: 1200
coverHeight: 750
toc: true
mathjax: true
coments: true
date: 2022-6-20 13:56:11
tags:
    - 博客
category:
    - [hexo博客]
---

使用hexo工具和gitee/github搭建自己的博客。
<!--more-->


## 1. 使用gitee（github）与hexo好处

- gitee 是国内的网站，相较于 github 访问速度更快；
- github是国外的网站，可以写一些比如科学上网之类的博客不至于发布不了。
- gitee和github免费方便，不用花一分钱就可以搭建一个自由的个人博客，不需要服务器不需要后台；
- hexo是大家使用非常广泛的静态博客；
- Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

## 2. 安装

### 2.1 安装Nodejs

Hexo 依赖 Node.js 和 NPM包管理，Node.js 安装后会自带NPM。因此，只需安装好node.js即可。

不管是macOS还是Windows系统，直接去[nodejs官网](https://nodejs.org/zh-cn/)下载安装包下载安装即可，属于傻瓜式安装（点击下一步、下一步。。。）这里不过多介绍。

### 2.2 安装git

由于后面我们需要用git管理仓库，所以这边需要安装git。方法也很简单，直接去[官网](https://git-scm.com/downloads)下载即可，也属于傻瓜式安装。

安装完成后，你的右键菜单栏会出现这两个标签：
![在这里插入图片描述](https://img-blog.csdnimg.cn/5405a50b983648439a26afb42fb74549.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_11,color_FFFFFF,t_70,g_se,x_16)

可以打开CMD，进入命令行，运行git命令看是否安装成功：

```java
git --version 
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/e134c476e62d436fb462d118e1c3868d.png)
能够输出版本号则表示正常。

### 2.3 安装Hexo

所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。

> 注：npm管理工具在安装好nodejs后就会自带，所以不需要额外安装。

打开cmd命令行或者右键选择`git bash here`，输入：

```bash
 npm install -g hexo-cli
```

即安装成功。

## 3. 建站

hexo安装完成后，即可开始初始化hexo项目，进行建站。

- 进入到你打算存放**博客源代码**的目录下，执行初始化命令：

```bash
# 初始化文件夹名为 hexo_blog
hexo init hexo_blog
cd hexo_blog
npm install
```

`hexo_blog`为存放博客的文件夹名字，你可以按照自己需求取，例如我这里取得就是`hexo_blog`。

初始化完成后，hexo_blog文件夹下的文件目录大致如下：

```bash
.
├── _config.yml  # 网站的配置信息
├── node_modules  # 应用依赖信息
├── package-lock.json
├── package.json  # 依赖包
├── scaffolds  # 模板文件
├── source  # 资源文件夹是存放用户资源的地方
│   ├── _drafts  # 草稿文件夹，刚初始化时可能不存在
│   ├── _posts  # 文章/帖子源码列表
└── themes  # 博客主题
```

其中`_config.yml`文件是配置文件，以后需要经常打交道的。里面的各个参数可以参考[网站](https://hexo.io/zh-cn/docs/configuration)。`source`文件夹是存放用户资源的地方，即以后你写的博客都存放在这里。

## 4. 启动

初始化项目后默认会安装相关的依赖，接着在命令行输入如下命令即可在本地运行查看博客 ：

```bash
# 启动服务，默认端口为 4000，启动服务后可以在浏览器输入 `http://localhost:4000` 查看效果
hexo server
# 简写方式
hexo s
# 还可以使用 -p, 指定 8888端口
hexo s -p 8888
```

## 5. 配置

建站完成后我们需要进行 配置，hexo 中主要有两项配置。

- 站点配置文件，路径为 `/_config.yml` ；
- 主题配置文件 ，路径是 `/themes/(自己下载的主题)/_config.yml` 。

站点配置文件主要是有以下几个基础选项

```bash
# Hexo Configuration
# 网站主标题，SEO元素之一
title: blog
# 网站副标题，可选
subtitle:
# 网站描述, SEO元素之一，用于告诉搜索引擎关于这个站点的描述
description: 
# 网站的关键词
keywords: 
# 网站作者
author: chh3213
# 网站使用的语言, 由于 Hexo 具备多语言配置，默认为英文，若需要中文语言，则修改如下
language: zh-CN
```

其余配置，可以具体参考hexo的[文档](https://hexo.io/zh-cn/docs/configuration)。

### 5.1 主题配置

熟悉了博客系统的操作后，接下来就是美化博客。Hexo 支持主题，我们可以根据[官网的创建主题教程](https://hexo.io/zh-cn/docs/themes.html)自己来设计，也可以直接在[主题商城](https://hexo.io/themes/) 中找现成的主题。

例如，笔者这边选择了[hexo-theme-yilia](https://github.com/litten/hexo-theme-yilia)

主题配置很简单，进入[hexo-theme-yilia](https://github.com/litten/hexo-theme-yilia) 的仓库，复制git clone的地址。

然后在`hexo_blog`文件夹目录下，git bash中输入：

```bash
git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/e5b734cc94ae43ec91a2ac1bbd315fe9.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)

下载后的主题在`hexo_blog`文件夹目录下的 `themes` 里面，如图：
![在这里插入图片描述](https://img-blog.csdnimg.cn/d19b756c2f294bbda9ce2be2532b22c1.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)
然后在 站点配置文件(`/_config.yml`) 中修改里面的 `theme: landscape` 为 `theme: yilia` 。

```yaml
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: yilia
```

最后启动主题即可。

```bash
hexo clean          #  启动主题前需要清除缓存与已部署的文件
hexo generate       # 生成静态网页
hexo s # 本地查看博客
```

## 6. 部署到gitee pages

我们使用git进行部署，可以将网站部署至私人服务器、也可以部署到免费的`github pages`或者`gitee pages`上。这边笔者选择的是`gitee pages`，因为`github pages`有时候不用点科学手段进不去。。。

### 6.1 创建一个gitee仓库

![在这里插入图片描述](https://img-blog.csdnimg.cn/4061678a8cbf4ecf8c0eba470e60b6d3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16) ![在这里插入图片描述](https://img-blog.csdnimg.cn/2fb7cdc9c4ce45ef8977de963812c9e0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)

> 注意：这里需要注意的一点是，如果你想直接通过域名就可以访问到你的博客个人网站，创建仓库的时候仓库名要和用户名保持一致。例如，我的gitee用户名为`caohuanhui`，我创建的仓库名是`caohuanhui`，那我访问的时候直接使用`https://caohuanhui.gitee.io/`就可以直接访问了。但是，如果我创建的仓库名和用户名不一样，比如我创建仓库的时候，仓库名为blog，那我访问的时候，就必须要域名+仓库名才能访问，如`https://caohuanhui.gitee.io/blog`。

> 至于是否选择开源，这边建议选择私有，因为这个仓库，还可以用来进行博客源代码备份，后面会提到。

点击创建即可，成功创建一个gitee仓库。

### 6.2 配置路径

- 进入刚创建的仓库，点击 `克隆/下载`，复制 Https 地址

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/cf1f7cdca9194330978e24b8ae763b47.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)==注==：这边并没有强制要求选择https方式，选择ssh方式也是可以的。

- 打开博客根目录，修改`_config.yml` 文件
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/3b64c7c0cd074a1b971ab4abda5a45c4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)
主要修改以下内容：

```yaml
deploy:
  type: git
  repository: https://gitee.com/caohuanhui/caohuanhui.git  # 刚才复制的 Https 地址
  branch: pages  # 部署到 pages 分支，如果该分支不存在，就会自动创建它
```

接下来我们还需要安装一个插件，在 `git bash` 下输入

```bash
npm install hexo-deployer-git --save
```

如果我们没有安装这个插件，此时直接执行部署的命令 `hexo g -d` 的话一般会报如下错误：

```bash
Deployer not found: gitee 或者 Deployer not found: git
```

### 6.3 开启GiteePages服务

进入到刚才创建的gitee仓库，找到`服务`，点击`Gitee Pages`开启`GiteePages`服务

![在这里插入图片描述](https://img-blog.csdnimg.cn/ff88f5062dbf488ba65c64556bccf8cb.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)
如果第一次开启`Gitee Pages`服务，会让你上传身份证进行验证，验证通过后即可使用。

进入到页面之后，选择`GiteePages`服务需要部署的分支，例如我这里要部署的分支为`pages`。推荐勾选上`强制使用HTTPS`，选择完毕之后点击启动（更新）便可开启GiteePages服务。

![在这里插入图片描述](https://img-blog.csdnimg.cn/44ea4dc9e28849b0918786ba23e719db.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)

接着开始部署。如果你还没配置git账号的话，会提示你输入账号密码，输入正确的账号密码后就部署成功了。

```bash
hexo g -d
```

每次部署成功后，都需要到GiteePages上点击更新。

### 6.4 github pages部署

如果使用github pages，则步骤 类似。

- 在 GitHub 新建一个名称为 `{username}.github.io`的仓库，`username`是你的github用户名
 
 打开根目录下的 _config.yml 文件，找到 Deployment ，修改如下：

 ```yaml
 # Deployment
 ## Docs: https://hexo.io/docs/deployment.html
 deploy:
   type: git
   repository: https://github.com/CHH3213/CHH3213.github.io.git
   branch: master
 ```
 
 与giteePages 完全一致，只是地址不同，以及branch这里一定要是master分支。

- 启动GitHub Pages
 
 在博客仓库的Settings界面，下拉找到GitHub Pages，生成博客网址
  ![在这里插入图片描述](https://img-blog.csdnimg.cn/b7475a7eac1e43869154be0cd09c5787.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)![在这里插入图片描述](https://img-blog.csdnimg.cn/abf5c3760cc247b5a8c7895f78ec5451.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)
部署成功后就可以通过`https://{github用户名}.github.io/` 访问个人博客了

> 在这里，要知道，GitHub Pages有两种类型：`User/Organization Pages` 和 `Project Pages`，而笔者所使用的是`User Pages`。
简单来说，User Pages 与 Project Pages的区别是：
>
>
> - User Pages 是用来展示用户的，而 Project Pages 是用来展示项目的。
>
> - 用于存放 User Pages 的仓库必须使用`username.github.io`的命名规则，而 Project Pages则没有特殊的要求。
> - User Pages 将使用仓库的 `master` 分支，而 Project Pages 将使用 `gh-pages` 分支。
> - User Pages 通过 `http(s)://username.github.io` 进行访问，而 Projects  Pages通过 `http(s)://username.github.io/projectname` 进行访问。

### 6.4. 博客源代码备份

至于上述博客源代码的备份（即`hexo_blog`文件夹下的备份），笔者同样使用的是gitee仓库。

![在这里插入图片描述](https://img-blog.csdnimg.cn/5c0c7a1f3a944ff4b559837f67f72343.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ0hIMzIxMw==,size_20,color_FFFFFF,t_70,g_se,x_16)
为了高效利用之前创建的部署gitee pages的仓库，所以这边并没有再额外创建一个仓库存放源代码，而是创建了**两个分支**，**一个分支（hexo）用来存放源代码，一个分支（pages）用来存放博客部署后生成的文件**，其中，存放博客源代码文件的分支设为主分支，如下图所示。
![在这里插入图片描述](https://img-blog.csdnimg.cn/da05861394544d7583b28358356d6c2a.png)

然后只需要通过一系列git操作，将本地源代码上传至仓库的hexo分支即可（这部分git基础操作就不在这介绍了）。

## 7. 写作

一般我们都会使用 `hexo new <title>` 来建立文章，这种建立方法会将新文章建立在 `source/_posts` 目录下，当使用 `hexo generate` 命令编译 时，会将其 HTML 结果编译在 public 目录下，之后 hexo deploy 将会把 public 目录下所有文章部署到 GitHub，这是整个 Hexo 流程。

这种建立文章方式的缺点是：若我们同时编辑多篇文章，只要其中一篇文章尚未编辑完成，也会随着 `hexo deploy` 一起部署到 GitHub，也就是 GitHub 可能会看到我们尚未完成的文章。

笔者个人的写作习惯是：

- 创建草稿 (drafts )
- 在草稿上进行写作
- 整理细节并在本地服务器上查看效果(server)
- 发布至正式的帖子上
- 生成静态文件并部署

### 7.1 创建草稿

```bash
# hexo new draft <title>
hexo new draft 博客名称
```

Hexo 提供 draft 机制，它将新文章将建立在 `source/_drafts` 目录下。生成的文件`博客名称.md` 是一个 markdown 文件，默认的草稿模板内容如下：

```bash
---
title: 博客名称
tags: 
---
```
> 在`/scaffolds`目录下可以修改draft、page、post(草稿、主页面、发布的文章)的模板。

### 7.2 在本地服务器预览草稿

```bash
hexo s --draft
```

Hexo 的 `Hexo server` 另外提供 `--draft` 参数，这让我们可以达到一边编辑 markdown 文章，一边使用浏览器预览的目的。

### 7.3 发布草稿

如果我们在本地服务器上校对完草稿细节后，可以将草稿发布为文章，否则在后续生成博客静态文件时不会被打包出来：

```bash
# hexo publish [layout] <filename>
hexo publish post 博客名称
```

输入命令后你可以发现发布的文章被转移到了`source/_posts/`上，这样就完成了本地的文章发布。

### 7.4 生成静态文件并部署

 Hexo框架的一项工作就是将源文件 markdown 最后生成为 HTML：

```bash
# 生成文件
hexo g
# 监控文件变化，并生成静态文件
hexo g --watch
# 生成文件并部署
hexo g -d
```

以上便是完整的部署过程了！

## 8. 常用hexo命令

```bash
hexo new "postName" #新建文章
hexo new page "pageName" #新建页面
hexo generate #生成静态页面至public目录
hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
hexo deploy #部署到GitHub
hexo help  # 查看帮助
hexo version  #查看Hexo的版本
hexo clean #清楚缓存
```

缩写：

```bash
hexo n == hexo new
hexo g == hexo generate
hexo s == hexo server
hexo d == hexo deploy
```

组合命令：

```bash
hexo s -g #生成并本地预览
hexo g -d #生成并部署
hexo clean & hexo generate & hexo server #重新生成并本地预览
```

## 参考资料

1. [https://hexo.io/zh-cn/docs/](https://hexo.io/zh-cn/docs/)
2. [https://su-lemon.gitee.io/post/5bd42e8c.html](https://su-lemon.gitee.io/post/5bd42e8c.html)
3. [https://developer.aliyun.com/article/794909](https://developer.aliyun.com/article/794909)
4. [Gitee+Hexo配置个人博客中的坑](https://singleplus.gitee.io/blog/2020/06/22/Gitee-Hexo%E9%85%8D%E7%BD%AE%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2%E4%B8%AD%E7%9A%84%E5%9D%91/)
