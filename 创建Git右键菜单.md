# 创建Git右键菜单

> 安装Git时，因为不想让右键菜单变得臃肿，所以取消了。但在后来的使用中发现挺不方便的，所以还是需要恢复这个右键菜单。因为常用的Git命令主要是`Git Bash Here`，所以只恢复一个即可。
>
> 下面讲解一下如何通过修改注册表的方式来创建Git右键菜单。



## 第一步，打开regedit

找到路径`HKEY_CLASSES_ROOT\Directory\Background\shell`

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210221164054.png)

## 第二步，新建项

右键`shell`，新增`项`，名字为：`open in git`（这个名字可以随意取）

![image-20210221164440133](https://cdn.jsdelivr.net/gh/huxuyf/images/20210221164445.png)

将【默认】值改为`Git Bash Here`，这是右键菜单中显示的**名称**。并新建一个`字符串值`，名称为`Icon`，数据为`git-for-windows.ico`的路径，这是右键菜单中显示的**图标**。



## 第三步，新建子项

在`open in git`上右键新建`项`，命名为`command`，默认值修改为`git-bash.exe`的路径，这是`Git Bash Here`右键菜单执行的命令。

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210221164815.png)



最终效果如图：

![](https://cdn.jsdelivr.net/gh/huxuyf/images/20210221165320.png)



**说明：可以通过Everything等工具查找相应文件的路径。**