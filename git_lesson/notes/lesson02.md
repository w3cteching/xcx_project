## 一、git上的watch,star,fork的区别


## 二、git提交时忽略不必要的文件

   .gitignore添加不必要提交的文件

   

## 三、git历史管理

    命令：git reset --hard commit_id

  >  说明：可以通过git reset 回退到以前的某个版本，也可以恢复到现在的某个版本

  >  所谓版本：即用git commit一次就是一个版本


  >  查看commit_id:  git reflog
   
1.放弃工作区的修改：git checkout -- 要放弃修改的文件名

2.放弃暂存区的修改：

       第一步：先将暂存区的文件回退到工作区

           git reset HEAD 要回退的文件
       第二步：到工作区，再用git checkouit放弃修改
       
          git checkout -- 要放弃修改的文件名
   
   3.回退分支版本：git reset --hard commit_id


## 四、git分支管理

   >默认git仓库只有一个master主分支


   >>master:通常用于发布产品的分支

   >>dev:开发分支

   >>bug:修复bug的分支

   >>feature:添加新功能的分支
   
   ### 分支常用命令：

    1.查看分支：git branch
 
  >注：分支前面带*表示是当前分支
       
    2.创建分支：git branch 分支名
    3.切换分支：git checkout 要切换的分支名

    4. 创建并自动切换到创建的分支上： git checkout -b 新分支

    5.合并分支

       git merge 要合并的分支名

   >出现冲突的场景：合并的分支和被合并的分支，都有修改，这时就会出现冲突

   >如果出现冲突：通常是手动解决
          采用当前：
          采用外来
          两者都要

      提交本地分支到远程：git push origin 要提交的本地分支

      删除本地分支：
      
          已合并：git branch -d 要删除的分支

          未合并：git branch -D 要删除的分支

      删除远程分支：

         git push origin :要删除的远程分支名


   添加当前分支与远程的跟踪：例如：当前分支是dev
   
    格式： git branch --set-upstream-to=origin/远程分支名

    例如： git branch --set-upstream-to=origin/dev


## 五、tag管理:即项目发布的版本管理 例如：v1.0.0  v1.2.1

version定义规则

>主版本号：表示项目的重大架构变更

>次版本号：表示较大范围的功能添加和变化

>增量版本号：一般表示重大bug修复

    例如：： 0.0.1

>查看tag: git tag

>添加tag；git tag tag名称

    例如：git tag v0.0.1
    
    给指定的commit_id添加版本：git tag tag名称 commit_id

    例如：git tag v0.2.0 00921af

>删除tag: git tag -d 删除的tag名

>推送tag到远程：git push origin 本地tag名

>删除远程tag:git push origin :本地tag名



## 六、git协作开发 

>协作开发分两种形式：

   1.国际化开发:主要利用pull Request请求，代码讨论，审核，最后由负责人合并请求代码

       大致步骤：
         第一步：先找到开源项目并fork到自己的仓库
         第二步：将form到自己仓库的开源项目克隆到本地

            git clone git@github.com:w3cteching/d2-crud.git

         第三步：修改克隆的代码（即参与贡献代码）

         第四步：提交到远程仓库

         第五步：发布pull Request请求，添加修改建议的标题和说明文字

         


>自有组织开发:公司内部：

    1.创建公司项目远程仓库

    2.添加项目协作者

        下边的操作都是其他组员的操作：

    3.克隆项目 git clone git@github.com:w3cteching/xcx_project.git

    4.本地操作添加代码并add,commit

    5.提交    

            git pull或
            git fetch origin  从线上摘取最新代码

            切换到当前分支上  yaojie_dingdan

            然后合并最新dev代码到当前分支:
               git rebase origin/dev 或
               git pull origin origin/dev 

            git push origin yaojie


            组长： git fetch origin  从线上摘取所有分支最新代码

            通过git merge 合并其他组员的分支到dev和master和组员提交的分支

            

    6.最后
          git push origin master
             和
          git push origin dev

            保持master和dev永远是最新的代码

       注意：如果git push不上去，

       git branch --set-upstream-to...........


   分支笔记补充：

      拉取远程分支到本地并合并：

         git fetch origin 拉取所有远程分支信息

         git branch 只查看本地分支
         git branch -r 查看远程分支
         git branch -a 查看所有分支（包括本地和远程分支）
         
         例如：想在本地dev分支上合并远程的master(或远程小组成员的分支)上的信息
         git checkout dev //先切换到当前分支

         git merge origin/master  //再合并远程的master分支到dev

        
    测试远程连接是否成功：ssh -T git@github.com

     如果测试成功会显示：Hi 远程帐号名! You've successfully authenticated,


    添加和删除远程地址：  

     添加远程仓库地址：git remote add origin 远程仓库地址
      
     删除远程地址： git remote rm origin

   设置远程推送的默认跟踪：git push 远程地址 要推送的分支 -u

     其中：-u 代表默认远程跟踪，下次可以直接输入 git push 回车


## 如何用可视化工具来操作git(即不用命令，用软件操作)

  git图形化软件：(git GUI)

    git GUI
    sourcetree: https://www.cnblogs.com/fisherbook/p/11397168.html
    webstorm:代码编辑器 内置集成git

    vs code：操作git

> 通常在公司中用命令为主，可视化为辅助（或结合两者的优势来使用）


## 七、使用github制作静态网站

   >适用场景：

      1.可以充当小型的个人博客网站（当然是免费哦，不用买空间和域名）

      2.你可以把个人简历推送上去，供其他人浏览
      
      3.....


  > 如何利用github制作静态网站呢？？？？

    主要通过git pages来实现静态网站

      第一步：找到要生成静态网站的仓库    例如：w3cteching/xcx_project
      第二步：打开这个仓库的settings-->GitHub Pages
      第三步：有两种实现静态网站的方式： 

        第一种：项目方式
        
           source:【推荐】

            选择用master主分支创建静态网站

            选择用master分支下的docs/创建静态网站  【推荐】

            无论哪种方式，都会生成一个可访问的网站：
            
            Your site is ready to be published at http://用户名.github.io/仓库名/.

      第二种：公司组织方式：类似于企业官网


       创建一个新仓库：仓库名必须是：  用户名.github.io  (用户名就是你登录的账号名)


         Theme Chooser:主题

## 八、使用码云来管理项目  


     github
     
     码云


