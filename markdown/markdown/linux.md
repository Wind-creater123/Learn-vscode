# ***linux***

## 理论题组

1. **linux**
   1. linux系统组成
    ==linux系统由linux系统内核及系统级应用程序（出厂自带的系统软件）组成==

    - <u>linux系统内核：提供系统 最核心的功能，调度各种硬件，系统</u>（如cpu，内存，网卡...
    - ==linux内核免费开源，任何人都可以下载源码并修改==
    - 系统级应用程序：出厂自带程序软件（如文件管理器，任务管理器...）
   2. *linux发行版*
   发行版：封装了完整的内核+系统级程序（任何人都可以封装，由于开源）

---

2. **文件夹**

    1. 根目录文件夹
      - /->为根目录（只有一个顶级目录）
      - 路径以/（根目录）开头其他/为层级关系
      - <u>以下全为/（根目录内文件）</u>
      - bin：基本用户命令二进制文件。包含所有用户都可使用的基本命令，==命令文件==
      - boot：==启动系统的文件==
      - dev：包含所有的==设备文件==
      - etc：所有系统和应用程序的==配置文件==
      - home：用户主目录。==大部分个人文件存储在这==
      - lib和lib64:基本共享库
      - media：移动媒体目录文件
      - mnt：临时文件区
      - opt：第三方应用软件
      - proc：进程和内核信息
      - root：管理员个人目录
      - run：运行中的临时数据
      - sbin：系统二进制文件
      - srv：服务数据
      - tmp：临时文件（定期清除）
      - usr：大部分用户应用程序，库，文档和源代码存储在此
      - var：存放经常变化的文件（日志...）
    2. 一切皆文件：==无论是硬件，软件，运行时数据，各种信息都有自己的文件夹，都摆在台面上，使用一个操作命令就可以访问所有资源==

---

3. **Vim**
Vim一个免费文本编辑器（开源）

   - 只需键盘操作
   - 连接虚拟机唯一可依赖的编辑器
   - 可以配置各种插件，集成一个开发环境
   - 不同模式
        1. ==（Esc返回）==命令模式
           - hjkl上下左右
           - w/b移动到下/上一个单词开头
           - 0/$移动到行首/行尾
           - gg/G移动到第一行/最后一行
           - i/a光标前/后插入
           - o/O在当前行下/上新开一行
           - x删除
           - ==dd删除（剪切）当前行==
           - dw删除一个单词
           - ==yy复制当前行==
           - ==p/P光标后/前粘贴==
           - ==u撤销（undo）==
           - Ctrl+r重做
        2. ==（i）输入模式==
        3. （：） 底线命令模式
            - :q退出(如果已经保存)
            - :==q!强制退出，不保存修改==
            - :==wq保存并退出==
            - :w保存
            - ==:set number 或 :set nu显示行号==
            - :set nonumber 或 :set nonu隐藏行号
            - :/keyword或:?keyword向下或上搜索keyword（按n下一个）

---

## 实践题组：题组一

1. vmware下载安装步骤

    - 下载安装vmware 17
     [下载安装教程](https://blog.csdn.net/air__j/article/details/142798842)
    - 检查：任务栏设置->网络设置->高级网络设置->vm net1和vm net8(win+r输入ncpa.cpl)
2. Ubuntu安装

   - 浏览器下载Ubuntu安装包
   - 打开VMware创建虚拟机，提供Ubuntu.iso
   - 其他一律下一步

3. 包管理器APT

   - ==sudo获取管理员权限（几乎所有命令前都加）==
   - ==apt调用包管理器== 
   - ==基本格式sudo apt ...==
   - ==update刷新软件源列表==
   - （full-）upgrade升级软件包（安全升级）
   - search ...搜索...
   - install ...安装软件包（可一次性安装多个）
   - remove ...卸载
   - purge ...彻底卸载
   - <u>autoremove自动清理（维护）</u>
   - （auto）clean缓存删除
   - show ...查看包信息

---

4. 网络配置
    1. 打开终端terminal
    2. 输入ifconfig
    3. 可能要sudo apt install net-tools
    4. 即可看到inet（ip地址）==（千万不要看错地址）==
    5. ip a也可（ens33网卡）

5. 远程连接
    1. sudo apt install openssh-serve在linux上下载ssh服务
    2. sudo ufw status查看状态
    3. sudo ufw allow 22开放22端口（在Ubuntu上）
    4. 打开powershell生成密钥ssh——keygen -t ed25519
    5. cat ~/.ssh/id_ed25519.pub显示公共密钥（私钥不能泄漏）==全部复制==
    6. ssh username@ip登录虚拟机
    7. mkdir -p ~/.ssh生成文件夹
    8. chmod 700 ~/.ssh设置权限
    9. echo “公钥” >> ~/.ssh/authorized_keys
    10. chmod 600 ~/.ssh/authorized_keys设置权限
    11. <u>完成上述步骤即可免密登录</u>
    12. scp （-r） -i [私钥路径] [本地文件路径] [用户名]@[ip]:[虚拟机文件路径]上传文件（上传文件夹）
    13. scp -i [私钥路径] [用户名]@[ip]:[虚拟机文件路径] [本地文件路径]下载文件
![上传](../markdown/picture/1.png)
![上传](../markdown/picture/2.png)
    14. 使用WinSCP也可

---

6. **linux命令**
基本格式：command -options parameter
命令+命令选项+参数

   - su -root [密码]获取管理员权限
   - ==ls获取当前工作目录的内容==(==带参数获取参数目录内容==)
      - -a同时获取 .开头的隐藏文件
      - -l平铺变竖向
      - -h易于观看的形式列出文件大小==（只能与-l同时使用）==
![ls](../markdown/picture/3.png)
   - cd parameter切换工作目录(不带参数，回到home目录)
![cd](../markdown/picture/4.png)
   - pwd打印当前工作目录路径
   - mkdir创建新目录
     - -p创建多层目录
   - touch [路径] 创建文件
   - ==cat/more 查看文件内容==
   - cp para1 para2 复制文件，复制para1到para2
       - -r递归，复制文件夹
   - move 移动文件（夹）
   - remove 删除文件
       - -r递归
       - -f强制删除
       - 支持通配符*
           - test*删除任何test结尾
           - *test删除test开头
           - *test*删除有test
   - ==chmod [权限] [文件（夹）]==
       - -R对文件夹内全部内容应用同样操作（无则只对文件夹）
       - u->user主体
       - g->group主体
       - o->other主体
       - 权限名称r，w，x
       - 权限可用数字1~8代替
   - ==systemctl控制第三方软件==
       - start开
       - stop停
       - status查看状态
       - enable开机自启
       - disable开机不自启
   - hostname查看主机名
    hostname set-hostname [name]修改主机名
   - ==ps 查看进程（ps -ef）==
       - -e查看全部进程
       - -f完全格式化形式展示全部信息 
   - kill 关闭进程
   - ==top 查看cpu，内存使用情况==
       - -p某个进程
       - -d设置刷新时间（默认5s）
       - -c显示进程详细目录
       - -n指定刷新次数
       - -d已批次方式执行top
       - -i不显示闲置进程
       - -u查找特定用户启动的进程
   - ==df硬盘使用情况==
       - -h人性化单位显示
   - ==iostat 查看cpu，磁盘相关信息==
       - -x显示更多信息
       - num1刷新间隔
       - num2查看次数
   - scar -n DEV num1 num2查看网络状态
   - which [命令]查看命令程序文件
   - find [起始路径] -name [文件名]

7.C语言输出hello world！
  
1. sudo apt install vim下载vim
2. vim hello.c编辑源文件
    ![vim](../markdown/picture/5.png)
3. sudo apt install gcc 下载gcc编译器
    ![gcc](../markdown/picture/6.png)
4. gcc hello.c -o hello编译程序
5. ./hello调用程序
    ![输出](../markdown/picture/7.png)