## git上的watch,star,fork的区别


## git历史管理

    命令：git reset --hard commit_id

    说明：可以通过git reset 回退到以前的某个版本，也可以恢复到现在的某个版本

    所谓版本：即用git commit一次就是一个版本

   
   1.放弃工作区的修改：git checkout -- 要放弃修改的文件名

   2.放弃暂存区的修改：

       第一步：先将暂存区的文件回退到工作区

           git reset HEAD 要回退的文件
       第二步：到工作区，再用git checkouit放弃修改
       
          git checkout -- 要放弃修改的文件名
   
   3.回退分支版本：git reset --hard commit_id


## git分支管理


## tab管理