# GitHub+Vscode代码管理教程
预备知识：
1. 安装GitHub Desktop并学习基础clone和push代码
    <p>视频教程： <a href="https://www.bilibili.com/video/BV13W411U7HY/?share_source=weixin_web&share_times=1&vd_source=b91afc82e63b14bfbf720e51d03b61b0" title="欢迎访问逐浪软件官网">【教程】使用GitHub Desktop管理你的项目</a>.</p>
    <p>文档教程： <a href="https://docs.qq.com/pdf/DZE15UXJVVkxzRlF2" title="欢迎访问逐浪软件官网">群文档汇总中【内部】github-desktop使用说明</a>.</p>
2. 安装vscode并安装插件Git Graph

本教程将会讲解github的一些基础概念、版本回退、创建与合并分支、代码冲突解决、以及在多人项目管理中的要求
作业：在本仓库中完成上述功能

## 1.git重要基础概念
* clone   将代码从云端下载到本地
* stash   暂存更改，可选择暂存某些更改进行提交（GitHub Desktop没有这个概念，只有changes,可以通过取消勾选不提交改更改）
![图片](resources\img_changes.jpg)
* commit    提交更改，commit之后以后就可通过回溯回到改版本，可以添加说明（说明最好讲清楚做了哪些更改，方便自己以后看，也方便别人）
![图片](resources\img_commit.png)
* push  将本地内容推送到远程仓库，推送之后别人才能通过pull或者进去GitHub网站看到你的更改
* pull  拉取代码，将云端代码更新到本地（通常需要解决冲突）
* revert    代码回退到某个版本，注意这里是回到这个版本更改前的状态
<a href="https://blog.csdn.net/qq_36441027/article/details/124032290">代码回退有另一个方法reset，想了解他们的区别点击这里</a>
* branch    分支，在多人管理中创建不同分支同时工作，在进行merge进行合并
* merge     分支合并，字面意思（通常需要解决冲突）

## 2.vscode中Git Graph插件
这个插件可以可视化仓库各分支间的关系，非常有用
先下载该插件![图片](resources\img_gitgraph.png)
节点图打开方式，两种方法，建议直接底部打开
![图片](resources\img_gitgraph2.jpg)
节点图如下图所示，不同颜色代表不同分支
下图中双击写错了，单击就可以了
![图片](resources\img_gitgraph3.jpg)
点击查看某个commit的信息
![图片](resources\img_gitgraph4.jpg)

## 2.代码版本回退
注意：进行代码回退前先把当前代码commit一次

按下图步骤操作进行revert
注意：revert操作为回到这次更改前的状态
![图片](resources\img_revert1.jpg)
界面右边是对应这次commit所作的更改，左边是他的更改前代码，右边是更改后的代码
上面操作同样可以在GitGraph插件进行（推荐且与上面等效）
![图片](resources\img_revert3.jpg)
点击revert后可能会出现报错，不要害怕，这是因为回退的代码和你当前代码有冲突需要解决，关闭弹窗后打开vscode
下图中绿色部分为冲突部分，要仔细看需要哪一部分，右下角使用合并编辑器更清晰，右上角上下箭头可以查看下一个冲突
![图片](resources\img_revert2.jpg)
解决完冲突后就回退完成啦！
## 3.创建与合并分支
### 3.1创建分支
创建分支的方法有好几种
1. Git Graph中在任意节点处右键 -> creat branch -> 输入分支名称（推荐）
2. GitHub Desktop中菜单栏Branch -> new branch -> 输入分支名
3. GitHub Desktop中History -> 选择任意节点右键 -> creat branch -> 输入分支名
### 3.2切换分支
1. Git Graph双击该分支
2. GitHub Desktop中菜单栏current branch -> 选择其他分支
### 3.3合并分支
示例：让这里dev_sgh合并到main
1.先双击main切换到该分支
2.右键dev_sgh选择合并到当前分支
![图片](resources\img_merge1.jpg)
弹窗选择确认
![图片](resources\img_merge2.jpg)
点击确认后可能会出现报错，不要害怕，这是因为合并的代码和你当前代码有冲突需要解决，解决冲突方法和代码回退中同理，解决完所有冲突后既完成合并

## 4.忽略某个文件
在实际应用中很多文件我们不希望他上云端（比如说编译产生的文件）
![图片](resources\img_ignore.jpg)
它会自动生成gitignore文件，如果想进一步了解该文件语法，自己百度或看下面链接
<a href="https://blog.csdn.net/nyist_zxp/article/details/119887324" title="欢迎访问逐浪软件官网">Git 开发必备 .gitignore 详解！</a>
## 4.多人项目管理
以自动步兵开发为例：
首先需要有一个稳定能用的主分支
1. 在做更改或研发前，在当前代码中开辟新的分支（新分支命名需要体现开发的工作，比如改进定位分支命名为dev_location）
2. 完成阶段性（或者完成一部分）任务后将更改commit一下，方便出错回退
3. 在代码debug完成后，merge到主分支中，merge的时候需要认真看每一项冲突（这一步最好有对机器比较熟悉的人一起来）
4. 完成合并后最好再测试一次看是否合并出错

## 作业
clone本仓库到自己电脑，完成上面操作
<<<<<<< HEAD
=======



## 其它教程
<a href="https://blog.csdn.net/weixin_43242506/article/details/123230514">Git Graph介绍与使用</a>
<a href="https://blog.csdn.net/qqw666666/article/details/125652869">GitHub Desktop使用教程</a>