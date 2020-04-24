## 一、git是什么

    git是开源分布式的版本控制技术
    github是一个利用git技术的开源托管平台

    代码托管平台：github，码云，gitlab等

    区分：git和github关系

    分布式(git)，集中式（SVN）

    分布式：没有中心，可以在本地独立完成，不依赖其他服务器
    集中式：必须有一个核心服务器，如果核心服务坏掉，那整体网瘫痪

## 二、git具体怎么玩？

   1.先安装一个git软件（也称git控制台）

     windows git软件下载地址：https://git-scm.com/download/win

   2.检测是否安装好git

      右侧--查看一下是否有git bash

   3.创建一个项目文件夹，例如：1906pro

   4.进入项目文件夹，输入git init 进行git初始化

   5.就可以在git的世界尽情玩起来

    window命令方式查看文件：dir
    清屏：cls

    mac查看文件：ls  -al 查看隐藏文件
    清屏：clear

## 三、git文件管理命令

    查看文件状态：git status
    将文件添加到暂存区：git add 目录名或要添加的文件名
    将暂存区的内容提交：git commit -m '提交说明'

    如果查看提交信息：git log或git reflog

     git日志简化，在一行显示：git log --pretty=oneline

     如果首次安装git，使用时需要配置git用户名和git邮箱

     配置用户名： git config --global user.name '你的用户名'
     配置邮箱：git config --global user.email '你的用户名'

     查看配置信息：git config --list


   > 注意：git管理的不是文件，管理的是”修改“


    ===========================================

    ## 如何将本地仓库文件提交到远程仓库

    以github为例演示，如何将本地项目上传到远程仓库

      1.注册github帐号

         sign up 注册
         sign in 登录

      2.登录并创建远程仓库
        
        点击登录后右上角的+号，选择new repo按照提示创建远程仓库
   
      3.在本地生成公钥和密钥  ssh   ************

      ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

      一路敲回车，然后在用户目录下的.ssh中生成两个文件：
        
         id_rsa: 密钥
         id_rsa.pub：公钥，

          将公钥文件复制到远程仓库的ssh中步骤：

          第一步：复制本地生成的id_rsa.pub里面的内容（一定要全选，不能敲空格）
          第二步：打开github并登录，找到用户名中的settings--->ssh and GpG keys--->点击new SSH keys

          第三步：将复制的id_rsa.pub里面的内容粘贴到第二步的key中，title随意

          第四小：点击 add ssh按钮完成



      4.连接远程

        添加远程：  git remote add origin 添加远程仓库地址

        远程地址格式：git@github.com:用户名/仓库名.git

        例如：git@github.com:w3cteching/xcx_project.git


        查看本地是否有远程连接信息：git remote -v



      5.推送本地代码到远程


        git push  推上去  本地-->远程

        git push origin master -u

        拒绝，报错：解决方案

        git pull 拉下来   远程-->本地

        git pull origin master (如果不行，继续往下)

        git fetch origin //获取远程所有分支

        git rebase origin/master


==============================

  从远程到本地：[推荐]

    git clone git@github.com:w3cteching/suyuhao_project.git

作业：

  1.将P7的月考机试题推送到github你注册的帐号下（提前创建好远程仓库）
  
  2.说课（用微信语音在微信群里总结回顾一天讲的东西）


        



      



