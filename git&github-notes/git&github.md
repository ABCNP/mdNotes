# git常用命令

## 基本操作

首次安装需设置用户名和邮箱

设置好的用户名和邮箱在``C:\Users\12262\.gitconfig``文件中可以查看(Windows家目录下)

> git config --global user.name 用户名 : 设置用户签名
>
> git config --global user.email 邮箱 :  设置用户邮箱(虚拟/真实)

> git --config  : 查看命令

> git config user.name : 查看用户名

> git config user.email :查看邮箱

初始化的作用就是在使用git之前需要获取一下管理权

前提先创建git本地库``G:\JAVAALL\Git&Github\Git-Space\git-demo\``

> git init : 初始化本地库

会出现一个.git的隐藏目录

> git status : 查看本地库状态

> vim xxx.txt : 创建一个文件,使用vim编辑器编辑内容后保存
>
> cat xxx.txt : 查看这个文件内容

再查看状态,就会有新的文件在工作区

> git add xxx.txt : 将文件添加到暂存区

Ctrl+L快捷键,清屏 

> git commit -m "日志信息" 文件名 : 将暂存区的文件提交到本地库

提交到本地库之后查看状态就没有这个文件显示了

> git reflog : 查看历史记录,版本号前七位

> git log : 查看详细日志,能看到提交者和时间,还有完整版本号

> git reset --hard 版本号 : 版本穿梭

.git\HEAD 文件中记录了当前指针指向的分支

.git\refs\heads\master 文件中记录了当前指针指向的版本号

这两个的位置是不会变化的,只是指针发生变化

底层就是玩的两个指针



**操作流程**

```txt
第一步:初始化本地库 -- 获取管理权
第二步:创建一个文件保存,使用vim编辑器
第三步:添加到暂存区(缓存可删除)
第四步:提交到本地库
第五步:修改文件,进行版本迭代
第六步:版本穿梭
```



## 分支操作

> git branch 分支名 : 创建分支 

> git branch -v : 查看分支 

> git checkout 分支名 : 切换分支 

>  git merge 分支名 : 把指定的分支合并到当前分支上

冲突合并:同一处有两套逻辑,需人为决定,手动修改一下就完事

**操作流程**

```txt
第一步:查看分支
第二步:创建新分支
第三步:切换分支
第四步:修改分支,修改完需提交
第五步:合并分支,需先切换到主分支再合并你想合并的分支
第六步:冲突合并
```



## github操作

> git remote -v : 查看当前所有远程地址别名 

>  git remote add 别名 远程地址 :起别名 

> git push 别名 分支 : 推送本地分支上的内容到远程仓库 

> git pull 远程库地址/别名 远程分支名 : 将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并

> git clone 远程地址 : 将远程仓库的内容克隆到本地

**操作流程**

```txt
第一步:创建github账号
第二步:创建远程仓库(远程库和本地库名称一致)
第三步:创建别名,(只是为了好记)
第四步:本地库推送到远程库(利用SSH免密方式)
第五步:拉取远程库代码(同步本地和远程)
```

拉取远程库代码,在github上修改之后,Commit changes提交,然后可以拉取到本地

克隆远程到本地无需登录账号



## SSH免密登录设置

`C:\Users\12262\.ssh\`路径下存放着ssh的公钥和私钥

该目录中打开gitbash

有的话直接

> cat id_rsa.pub

查看是不是绑定自己的github邮箱不是的话,是的话直接用,不是的话将`.ssh`文件删除,在用户目录下打开gitbash,输入以下命令重新生成,(自己邮箱)

> ssh-keygen -t rsa -C ningpeng97@163.com

什么都不做敲三次回车,就生成好了

> cd .ssh

继续查看`id_rsa.pub`,存放着公钥

> cat id_rsa.pub

复制公钥内容,到github打开个人中心,Settings --> SSH and GPG keys --> New SSH key --> 随便取个名字,粘贴



注意:github对ssh秘钥做了升级,输入以下命令

> ssh-keygen -t ed25519 -C ningpeng97@163.com

会生成两个新的秘钥对

查看新的公钥





# idea集成git

**操作流程**

```txt
第一步:配置忽略文件
第二步:idea集成git
第三步:用idea初始化本地库
第四步:添加暂存区
第五步:提交本地库
第六步:修改代码/添加代码后再添加暂存区提交本地库
第七步:创建分支,修改主分支代码和新分支代码
第八步:合并分支,冲突合并并提交
```



## 配置忽略git文件

```txt
第一步:在家目录下创建,C:\Users\12262\git.ignore文件,将模板粘贴保存
第二步:C:\Users\12262\.gitconfig中引用git.ignore
添加以下代码:(用正斜线分隔)
[core]
	excludesfile = C:/Users/12262/git.ignore
```

模板

根据需要添加忽略

```txt
# Compiled class file
*.class

# Log file
*.log

# BlueJ files
*.ctxt

# Mobile Tools for Java (J2ME)
.mtj.tmp/

# Package Files #
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar

# virtual machine crash logs, see 
http://www.java.com/en/download/help/error_hotspot.xml
hs_err_pid*
.classpath
.project
.settings
target
.idea
*.iml
```



## idea定位git

idea中File --> Settings --> Version Control --> Git -->Path to Git executable --> git程序路径(D:\javasoftware\Git\bin\git.exe) --> Test -->显示版本信息即配置成功



## idea初始化本地库

VCS --> Import into Version Control --> Create Git Repository --> 选择要管理的项目

(看见文件变红)



## idea添加文件到暂存区

选择要提交的文件右键 --> Git --> Add --> 文件变成绿色

(也可以直接添加整个项目)



## idea提交文件到本地库

选择要提交的文件/项目右键 --> Git --> Commit Directory --> 在commit Message 写提交信息



## 切换版本

通过点击左下角Version Control --> log 可以查看提交版本日志

如果没有显示,那么找到左上角git的时间标志,点击show history,就会出现,还没有就百度解决



选择要切换的版本右击 --> Checkout Revision



## 创建分支

方式一:点击右下角Git:master --> New Branch --> 输入分支名

方式二:任意处右键 --> Git --> Repository -->  Branches --> New Branch --> 输入分支名



## 切换分支

右下角点击想要切换到的分支 --> checkout



## 合并分支

正常合并就正常合并

切换到主分支上,右下角选择你想要合并的分支 --> Merge intoCurrent

冲突合并会弹出提示框 --> 点击Merge --> 手动解决冲突代码

左边是主分支,右边是其他分支,中间的显示最终代码,手动合并后,点击Apply即可

然后继续将主分支代码添加暂存区提交本地库,完成最终代码



# idea集成github

**操作流程**

```txt
第一步:添加github账号
第二步:分享代码到github
第三步:推送代码到远程库
第四步:拉取远程库代码到本地
第五步:克隆远程库代码到本地
```



需要提前安装github插件

## 设置github账号

settings --> Version Control --> github --> 点击+号添加账号

方式一:账密登录

(推介)方式二:口令登录

点击enter token --> 输入token --> login

生成口令:github --> settings --> Developer settings --> Personal access tokens --> Generate new token --> 起名字,所有权限勾选 --> Generate token --> 将生成的token复制保存(只显示一次,保存谨防丢失)

> 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



## 分享代码到github

VCS --> import into version control --> share project on github --> 输入信息 --> share



## 推送代码到远程库

方式一:选择项目右键 --> Git --> Repository --> push

方式二:VCS --> Git --> push 

但是默认用的是https链接,建议用ssh链接

复制ssh链接 --> 点击分支 --> Define Remote --> 起别名,将ssh链接粘贴 --> ok



## 拉取代码到idea

修改远程代码并提交 --> VCS --> Git --> pull -->选择ssh方式拉取  



## 克隆代码到本地

关闭idea删除项目代码 --> 重新打开idea --> 初始界面点击check out/get from version control  --> 选择git方式 --> 输入github的ssh连接 --> test --> clone



# idea集成gitee码云

**操作流程**

```txt
第一步:注册登录码云
第二步:创建仓库
第三步:idea集成码云(安装插件)
第四步:登录马云账号
第五步:推送代码到码云
第六步:从gitee拉取代码到idea
第七步:复制github项目到gitee
第八步:强制同步github代码到gitee
```



## idea集成gitee

settings --> Version Control --> gitee --> create API token --> 登录码云账号密码 --> apply



## 分享代码到gitee

提前在gitee创建远程库

VCS --> import into version control --> share project on gitee --> 输入信息 --> share



## 推送代码到gitee

方式一:选择项目右键 --> Git --> Repository --> push

方式二:VCS --> Git --> push 

gitee建议使用https链接

复制https链接 --> 点击分支 --> Define Remote --> 起别名,将https链接粘贴 --> ok



## 拉取代码到idea

操作同github

其他操作和github相似



## 复制github项目到gitee

将github代码迁移到gitee

在gitee中新建仓库什么都不填下拉  或者右上角 --> 选择导入已有仓库 --> 输入github的https链接 --> 



点击项目名后的刷新按钮,可强制同步github代码到gitee



# gitlab

需在虚拟机操作



## idea集成gitlab

先安装gitlab插件

参考:尚硅谷技术课程系列之Git V2.0.pdf的gitlab章节



# Github5个隐藏神级技巧

鱼皮:

https://www.bilibili.com/video/BV1q54y1f7h6/?spm_id_from=333.1007.top_right_bar_window_custom_collection.content.click&vd_source=e3c1a57c5f8561699e8f4460cc5ae27d

## 高级搜索

直接按s,聚焦到搜索框,利用高级搜索功能提供的搜索限定符搜索精确项目

搜索框下面的导航栏最底下有Advanced search,输入限定的搜索范围,可快速查找

官方文档:在github上搜索,有更多搜索限定语法

https://docs.github.com/cn/search-github/searching-on-github/finding-files-on-github

## 文件查看技巧

直接按t,可对仓库所有文件实时搜索,点击文件后,

直接按L,可以快速跳转的某一行,然后点击行号可快速复制代码,

直接按B,可快速查看文件改动情况

ctrl+k,调出暗藏的命令面板,进行各种查看操作



## 阅读代码技巧

直接按。，调出网页版VScode编辑器，项目直接打开，无需下载到本地，就是vscode的线上版，还可安装插件





## 在线运行项目

在项目地址前加上`gitpod.io/#/`

有待研究//todo(第三方平台)



## 项目推送

Github的Explore界面右上角有个Get email updates,获取邮件更新,根据喜好,定期推送自己感兴趣的优质项目



# 上传md笔记(Typora)至github

参考:https://blog.csdn.net/qq_39588003/article/details/115670602

```txt
第一步:创建笔记文件夹(md笔记的图片设置相对路径)
第二步:将笔记放在这个文件夹(将笔记做好分类)
第三步:上传笔记
```

和上传代码一样步骤

> git add * : 将所有的文件添加到暂存区

> git commit -m "提交信息" 

> git push -u origin master

