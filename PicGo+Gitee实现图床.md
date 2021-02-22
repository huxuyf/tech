# PicGo+Gitee实现图床

## 一、安装

1. PicGo
2. gitee插件

PicGo的[下载地址](https://github.com/Molunerfinn/PicGo/releases)

下载安装好后，可以看到这样的界面：

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222214520.png)

![PicGo](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222211623.png)

然后，点击**插件设置**，搜索`gitee`

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222211718.png)

这两个插件的作用差不多，只是设置不太一样。我这里安装了第二个。

**注意：只有安装了node.js后才能安装插件。**



## 二、创建gitee图床仓库

### 1、创建仓库

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222212245.png)

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222212407.png)

原本这样就已经完成了Gitee的图床设置，但我多此一举，在仓库里的设置做了修改，导致我后面上传图片失败。

**记住：在仓库的基本设置中，【是否允许仓库文件在线编辑】是一定要选中的！**

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222212536.png)

### 2、生成令牌

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222212746.png)

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222212807.png)

点击【生成新令牌】按钮，

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222212936.png)

私人令牌描述，随意命名。权限只要选择`projects`即可。

点击【提交】按钮，会让你输入密码验证。然后会跳出一个令牌已生成的提示，记得复制上面的令牌。**这个令牌只会出现一次。**



## 三、使用

### 1、配置插件

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222213513.png)

1. repo，须以`<用户名>/<仓库名>`的形式，我的用户名是`huxuyf`，新建的仓库名为`images`![image-20210222214002036](C:\Users\user.ZJHUXUYF1Y\AppData\Roaming\Typora\typora-user-images\image-20210222214002036.png)
2. branch，分支名，默认就是master
3. token，即刚才生成的私人令牌
4. path，默认是上传到根目录，可以上传到子目录下，我这里就是上传到202102目录下
5. customerPath
6. customerUrl

![image-20210222214227536](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222214232.png)

设置**快捷上传**的快捷键为`Ctrl+Alt+P`

### 2、测试

使用截图工具（如：Snipaste），截图，然后按`Ctrl+Alt+P`快捷键，查看是否能成功上传。

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222215306.png)

在【上传区】可以选择上传到不同的图床。

**注：这里选择哪个图床，就是把哪个图床作为默认图床。效果等同于在`图床设置`中设为`默认图床`。**

- 链接格式

  - 将上传后的链接自动生成相应的格式，一般常用Markdown格式

- 快捷上传

  - 剪贴板图片，可以把剪贴板中的图片上传
  - URL，将图片URL对应的图片上传

  