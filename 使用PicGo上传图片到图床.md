# 使用PicGo上传图片到图床

## 前言

这里涉及到了**PicGo**，**Github**，**Typora** 。

通过**PicGo**上传图片到**Github**的图床，然后在**Typora**中使用。



## 一、准备工作

### 1、Github

首先在**Github**上新建一个专门用于存放图片的仓库。我这里命名为**images**。

![github仓库截图](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220143849.png)

新建仓库的步骤跟其他仓库的方式无二。



**为了使用PicGo，需要获取一个token。**

在用户设置**setting**中选择**Developer settings**，

![Developer settings](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220144134.png)

然后选择**Personal access tokens**，点击**Generate new token** ,

![Personal acccess tokens](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220144259.png)

新建一个访问token，**记得生成后复制一下，找个地方保存一下，以后用得着**

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220144538.png)

### 2、PicGo

#### 2.1 下载

[源码](https://github.com/Molunerfinn/PicGo) [下载地址](https://github.com/Molunerfinn/PicGo/releases)

#### 2.2 Github图床设置

![PicGo设置](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220145215.png)

下载安装后，找到**图床设置**-**GitHub图床**，说明如下：

1. 设定仓库名，之前创建的存放图片的仓库，记得带上用户名；

2. 设定分支名，选择默认的分支名**main**

3. 设定Token，就是上面获取的Token

4. 指定存储路径，因为我是把图片直接存放在根目录下，没有建子目录，所以留空

5. 设定自定义域名，这里采用了CDN加速，前面**https://cdn.jsdelivr.net/gh/**保持不变，后面就是**用户名/仓库名**即可

   

#### 2.3 PicGo设置

![PicGo设置](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220150439.png)

1. 修改快捷键，默认是mac的设置，改成win中的设置，`Ctrl+Alt+P`
2. 上传后自动复制URL
3. 开机自启，因为很常用，所以建议开启



### 3、Typora

在**Typora**中，选择**文件**-**偏好设置** 

![Typora图像设置](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220145909.png)

**PicGo路径**是本地电脑**PicGo.exe**的路径



**验证图片上传选项**

![验证成功](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220193259.png)



## 二、使用PicGo

### 1、快捷键上传（推荐）

使用截图工具截图完成后，按`Ctrl+Alt+P`，PicGo即可自动上传图片，上传成功后，剪贴板中自动获取Markdown格式的URL，可以直接在Typora中粘贴使用。

**注：单次只能上传一张图片。**



**上传成功**

![上传成功](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220193416.png)

### 2、界面上传

打开PicGo主界面，可以将图片拖放到该界面进行上传。

![PicGo上传](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220151057.png)

**注：单次可以上传多张图片。**

![上传演示](https://cdn.jsdelivr.net/gh/huxuyf/images/20210220151818.gif)

## 三、PicGo插件

[Awesome-PicGo](https://github.com/PicGo/Awesome-PicGo) 