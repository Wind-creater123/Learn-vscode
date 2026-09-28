# ***GIT***

## *概念*

1. git与github

- ==git：版本控制系统==。类似于Word文档（记录文档），用来管理你的代码的不同改变。**跟踪和管理代码的变化**
- ==github：在线代码托管平台==。可以将你的代码push到github上，永远保存
- 关系：可以在本地使用git管理代码，然后push到github进行云端备份。

2. git的重要性
    - Git记录了每一个代码文件的变化历史，包括谁，在什么时间，修改了哪一行代码。如果对更改后悔，可以回退至之前任何一个版本，相当于“后悔药”，拥有更多尝试机会，降低风险
    - github提供仓库，所有人都可以提交，获取最新代码，从而提高效率。
    代码备份，防止方向错误，代码错误而无法更改。
    快速查找到导致bug出现的修改，从而定位bug，方便维护

## *git命令*

![截图](../markdown/picture/test.png)

![截图2](../markdown/picture/test2.png)

## 实践操作
==初次使用，需登记==
![初始](../markdown/picture/9.png)
- **创建文件夹，初始化** 

![初始化](../markdown/picture/1.png)
提交
![初始化](../markdown/picture/8.png)

- **连接仓库并提交**
复制粘贴github地址
![初始化](../markdown/picture/10.png)
master需改为main，才能正常push
![初始化](../markdown/picture/2.png)
![初始化](../markdown/picture/4.png)
授权
![初始化](../markdown/picture/3.png)

- **github**
创建公共库
![初始化](../markdown/picture/5.png)
修改文件
![初始化](../markdown/picture/6.png)

- **本地pull**
pull!!!
![初始化](../markdown/picture/7.png)

origin为远程库命名，可改，但最后别改，别用master用main做主
==git commit错误可用git status==

[gihub公共库](https://github.com/Wind-creater123/my-project.git)