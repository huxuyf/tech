# NPM的使用

> NPM是随NodeJS一起安装的包管理工具，主要用于安装NodeJS模板

## 查看是否已安装NPM

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222160420.png)

## 更换NPM镜像

默认官方镜像为：https://registry.npmjs.org，但比较慢，推荐更换成淘宝的NPM镜像。

`npm config set registry http://registry.npm.taobao.org/`

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222160750.png)

`npm get registry` ，查看当前的镜像地址。



## 安装模块

```bash
npm install <Module Name>
npm install <Module Name> -g
```

前者是本地安装，将安装包放在`./node_modules`下（运行npm命令所在的目录）；

后者是全局安装，将安装包放在`node`安装目录下。



## 查看安装信息

`npm list`，查看当前目录下安装的模块

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222161307.png)

查看全局是这样：

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210222161439.png)



## 更新模块

```bash
npm update <Module Name>
```



## 卸载模块

```bash
npm uninstall <Module Name>
```



