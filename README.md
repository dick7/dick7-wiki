# dick7-wiki
我的wiki

基于mkdocs
＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝
以学代练
ref:

搭建自己的wiki知识管理系统
0.442
2019.03.31 16:26:32
字数 687阅读 2728
搭建自己的wiki知识管理系统

[图片上传失败...(image-692256-1554020719004)]

本文小编将带大家从零开始搭建一个属于你自己的wiki系统。
开源的wiki系统有很多，比如：

    大名鼎鼎的MediaWiki
    小巧易用的DokuWiki
    国内开源的minDoc
    Gitbook
    Docsify
    Hexo
    MkDocs

小编选择使用的是MkDocs，因为它部署和使用都非常的简便，特别适合作为个人wiki知识管理系统。简单的说MkDocs就是将Markdown文件转换成静态的HTML网站，然后既可以在本地直接访问，也可以托管到服务器或者GitHub。

    实战开始

1.安装MkDocs
1.1 Ubuntu系统


sudo apt-get install mkdocs

1.2 Windows系统

    MkDocs目前支持Python2.7,3.4,3.6,3.7版本

    安装Python（请参考Python官网教程）
    安装pip

pip install --upgrade pip

    安装MkDocs

pip install mkdocs

1.3 确认是否安装正确

mkdocs --version

2.创建一个Wiki

mkdocs new my-wiki
cd my-wiki

成功创建后，就如下图所示：
image

    docs文件夹下存放的就是自己写的Markdown文章，系统默认会生成一个index.md文件
    mkdocs.yml是wiki网站的配置文件（主题、目录、语言等）

3.预览wiki

    首先启动mkdocs服务

mkdocs serve

    然后打开浏览器输入127.0.0.1:8000访问wiki

如果以上步骤都执行成功，你将看到如下界面：
image

至此，一个wiki系统已经搭建完成，下面我们来学习一下如何向wiki系统中添加新的内容吧！
4.添加新内容
4.1 添加新的文字内容

    首先在docs文件夹下面创建test.md文件，并使用你喜欢的markdown编辑器写入内容，如下所示：

This is a new page.

# 一级标题

## 二级标题

### 三级标题

    编辑mkdocs.yml文件，写入以下内容：

nav:
    - Home: index.md
    - First: first.md

4.2 插入图片

在docs文件夹下创建images文件夹，并将图片放入此文件夹，然后在markdown文件中引用：

![mkdocs](images/mkdocs.png)

5.更换主题

mkdocs有多个主题可供选择，以满足不用用户的喜好，在此小编向大家推荐Material主题。
5.1 安装Material主题


pip install mkdocs-material

5.2 配置wiki使用Material主题

打开配置文件mkdocs.yml，写入以下内容：

theme:
  name: 'material'

6.将你的wiki站点托管到GitHub

    创建一个新仓库。 比如: https://github.com/user_name/repository_name
    初始化你的本地仓库（wiki）, 添加远程仓库，提交本地修改并推送到远程仓库

cd my-wiki
git init
git add remote https://github.com/user_name/repository_name
git add .
git commit -m "first commit"
git push origin master

    部署你的wiki站点

mkdocs gh-deploy

现在你的wiki站点（HTML文件）在gh-pages分支，你的wiki站点（markdown文件）在master分支。

*通过以下网址访问你的wiki

https://user_name.github.io/repository_name
