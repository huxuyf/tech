# 基于Github使用Hexo搭建个人博客

## 前言

Github提供了pages服务，也就是可以在Github上搭建个人**免费**网页。但如果从零开始去写html代码，这与目前快速发展的网络时代有点背离。而现在有很多技术可以自动生成博客系统。比如Jekyll、Hugo、Hexo等。



### 为什么会选择Hexo？

上面说的三种技术都有可取之处，至于为什么会选择Hexo，下面罗列一下原因：

* 能够一键部署到GitHub上
* 支持Markdown
* 有丰富的主题
* 有丰富的插件



### 提前要说的话

网上的文章都说比较容易，但实际上还是有一定的技术门槛，所以只适合一些程序员，而不是普通用户。如果普通用户想学会，需要花不少的时间，反而会把自己带偏。估计很多人的第一篇博客都是说自己是怎么搭建这个博客的。

所以我推荐普通用户还是选择一些比较靠谱的有博客的网站去写博客。这样有两个好处：一、门槛低，不需要自己去搭建；二、也是免费的。



## 准备工作

### 一、Github的准备

一般来讲，看到这里，应该是有Github账号了。这里主要讲一下Github的pages怎么去设置。



#### 1.1 新建仓库

网址：https://github.com/new

![新建仓库](https://gitee.com/huxuyf/images/raw/master/2021/02/20210222234506.png)

这里的关键点是仓库的名字必须是：<你账号名>.github.io

因为我已经创建过了，所以有个错误提示。

我这里是想把http://huxuyf.github.io作为博客的首页。其实还有另外一种做法。再创建一个仓库，比如叫：blog，然后把所有文件传到blog仓库中，我们可以使用http://huxuyf.github.io/blog作为个人博客的首页。



#### 1.2 创建index.html

在仓库根目录下创建**index.html**文件，里面写一些简单的html代码。比如：

```html
<html>
<head>huxuyf的个人网站</head>
<body>
<h1>这个在GitHub上的第一个网页</h1>
</body>
</html>
```



#### 1.3 查看网页是否正常显示

过几分钟，可以用浏览器打开网址：https://huxuyf.github.io/，进行查看网页是否正常显示。如果能正常显示，那就说明一切正常了。

如果只是使用GitHub显示一个单网页，我们只需要在WEB上编辑**index.html**即可完成任务，不需要进行以下的步骤了。

但我们的目标肯定不只局限于此。



### 二、安装Node.js

Hexo是基于Node.js，所以电脑上一定要先安装Node.js。

打开Node.js官网进行下载：https://nodejs.org/zh-cn/download/

这里主要注意一点，**如果你还在使用WIN7，需要注意一下不要下载最新版的**。我下载的版本是：**node-v12.18.4-x64.msi**，可以到这里下载：https://nodejs.org/zh-cn/download/releases/



### 三、安装Git

Git主要是用于将Hexo在本地生成的文件上传到GitHub上（这里我的理解）。但Git的作用远不止如此。如果会经常用到GitHub，那Git这个工具是必不可少。（我后面还会专门出一篇学习使用git的文章）

这里我下载的是命令行工具。也是去官网下载：https://git-scm.com/



### 四、Hexo的准备

Hexo的安装不同于上面的软件。它是通过Node.js中的npm来安装的。

```shell
npm install hexo-cli -g
npm install hexo-deployer-git --save
```

第一行是安装hexo，第二行是将hexo的文件deploy到GitHub上需要的东西。



在本地创建一个文件夹用于保存hexo创建的文件。比如我在D盘创建了一个D:\Hexo 目录。



## 配置

上面是基本的准备工作。还有比较繁琐的配置工作。

### 一、Git的连接

在https://pages.github.com/上介绍如何使用git来操作GitHub步骤很简单，但我觉得应该是缺少了一些操作，所以就不建议去看了。

首先得让GitHub认可你本地电脑上传的连接。这部分本来应该在初步使用git的时候应该做的事情，但因为我们的基础是零，所以还得介绍一下。

不过如果觉得繁琐的话，大家可以先跳过这部分内容，只是在使用git连接Github时会提示输入账号、密码。等以后再来设置。



#### 1.1 检查个人用户文件夹

进入个人用户文件夹，如：`C:\Users\user.ZJHUXUYF1Y\` ，看有没有一个`.ssh` 的文件夹，如果有，说明可能之前已经生成过相应的SSH公钥私钥，那就可以跳过第二步，直接到第三步。这里假设没有。



#### 1.2 生成SSH公钥私钥

打开Git Bash，输入以下命令：

```bash
ssh-keygen -t rsa -C "shingu@gmail.com"
```

> 注：后面的*shingu@gmail.com* 是我个人邮箱，应改成自己邮箱地址

接着会提示输入密码、确认密码。密码可以为空。

操作后，就能在之前的.ssh文件夹下看到**id_rsa**和**id_rsa.pub**两个文件了。我的理解：前者是私钥，后者是公钥。



#### 1.3 在GitHub中添加公钥

打开GitHub的设置

![设置](https://gitee.com/huxuyf/images/raw/master/2021/02/20210222234521.png)

点击菜单【SSH and GPG keys】，然后点击按钮【New SSH key】

![新建SSH Key](https://gitee.com/huxuyf/images/raw/master/2021/02/20210222234527.png)

Title 随便写，Key的内容就是文件**id_rsa.pub**的内容（用记事本之类的工具打开查看即可）

![增加SSH Keys](https://gitee.com/huxuyf/images/raw/master/2021/02/20210222234532.png)



#### 1.4 测试连接

经过上述设置，应该设置成功，本机可以通过git连接GitHub了。输入以下命令进行测试：

```shell
ssh -T git@github.com
```



#### 1.5 个人用户信息设置

最后还需要通过git配置一下个人用户信息。

```shell
git config --global user.name "ShingU"
git config --global user.email  "shingu@gmail.com"
```



### 二、Hexo的配置

#### 1、Hexo的初始化

进入之前创建的Hexo文件夹：D:\Hexo，然后进入Git Bash，执行以下命令：

```bash
hexo init
npm install
```

第一句是初始化hexo，会在我的Hexo目录下创建一些需要的东西。第二句是按照一些需要的东西。只要照做就行。



#### 2、编辑文件_config.yml

常见修改的地方如下：

![_config.yml](https://gitee.com/huxuyf/images/raw/master/2021/02/20210222234537.png)



![Deployment](https://gitee.com/huxuyf/images/raw/master/2021/02/20210222234539.png)

详细配置可以看[这里](https://hexo.io/zh-cn/docs/configuration) 。第一次就按照上面的修改。以后可以慢慢改。



## 进入正题

### 1、写博客

```
hexo n <文章标题>
```

会在`D:\Hexo\source\_posts`目录下生成一个`<文章标题>.md`的文件。然后编辑这个文件即可。

当然也可以直接在这个目录下新建.md文件。



### 2、生成静态文件

md文件无法在网页上直接查看，需要生成静态文件。

```
hexo g
```



### 3、上传到服务器

```
hexo d
```



### 4、Hexo常用命令

```bash
npm install hexo -g #安装Hexo
npm update hexo -g #升级
hexo init #初始化博客
hexo n "我的博客" == hexo new "我的博客" #新建文章
hexo g == hexo generate #生成
hexo s == hexo server #启动本地预览服务预览
hexo d == hexo deploy #部署到github发布到网络
hexo g -d # 先生成静态文件，再部署上去
hexo server #Hexo会监视文件变动并自动更新，无须重启服务器
hexo server -s #静态模式
hexo server -p 5000 #更改端口
hexo server -i 192.168.1.1 #自定义 IP
hexo clean #清除缓存，若是网页正常情况下可以忽略这条命令
```



## 高级篇

### 1、美化博客（更改主题）

#### 1.1、寻找合适的主题

进入[官网](https://hexo.io/themes/)，查找自己觉得好看的主题。建议找中文版的主题。



#### 1.2、获取主题

比如我选择了**[codeteenager](https://github.com/codeteenager/hexo-theme-codeteenager)** 这个主题，进入克隆。

按照提示：

```bash
git clone git@github.com:codeteenager/hexo-theme-codeteenager.git themes/codeteenager
```



#### 1.3、修改主题

3.1 修改hexo的配置文件

`_config.yml` 在 # Extensions 中，修改 theme 为 **codeteenager**



#### 1.44、更新

```
hexo clean
hexo g -d
```



### 2、使用source分支保存源码

#### 2.1、创建source分支

在Github上创建source分支

![创建source分支](https://gitee.com/huxuyf/images/raw/master/2021/02/20210222234545.png)

#### 2.2、初始化本地仓库

在Hexo目录下执行下面的命令，建立本地仓库与远程仓库的关联：

```
git init
git remote add origin git@github.com:huxuyf/blog.git
```

![初始化Hexo](https://gitee.com/huxuyf/images/raw/master/2021/02/20210222234549.png)

#### 2.3、推送源码

```bash
git push -u origin source
```



### 3、插入图片的问题

这是一个比较麻烦的问题。原本以为Hexo可以比较好的适应Markdown书写的文章，但发现会比较麻烦。看来博客只能写纯文字的东西了。

我习惯于Markdown写的文章中的图片是存放在文章同级的同名文件夹下。

![Typora设置图像](https://gitee.com/huxuyf/images/raw/master/2021/02/20210222234552.png)

Hexo中确实也可以在 `config.yml` 文件中的 `post_asset_folder` 选项设为 `true` ，将在创建文章时自动创建文件夹来存放图片。但是在生成静态文件时，无法正常显示这个图片，只有通过下面的改造才行。

```
{% asset_img example.jpg %}
```

但这样的话，对于图片较多的文章，修改起来比较麻烦了。



有个插件可以解决这个问题：`hexo-image-link`，但我在使用时发现有点问题。

后来我刚才使用图床的方式解决了。

