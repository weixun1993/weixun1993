## git版本控制系统

#### 	版本控制系统

​	1.记录历史版本信息（记录每一次修改的记录）

​	2.方便团队相互之间协作开发

#### 	常用的版本控制系统

- ​	cvs/svn ：集中式版本控制系统

- ​	git ：分布式版本控制系统

  #### git工作流程

  ##### git工作原理

  ​	工作区：写代码区域		

  ​	暂存区：临时存储用        

  ​	历史区：生成历史版本	

  

  ##### git基本命令

  

  删除文件		git rm filename

   

  版本回退：可以将当前仓库回退到历史的某个版本		git reset 

  ​	第一种用法：回退到上一个版本（HEAD代表当前版本，有一个^代表上一个版本，以此类推）

  ​			git reset --hard HEAD^

  ​	第二种用法：回退到指定版本(其中d7b5是想回退的指定版本号的前几位)

  ​			git reset --hard d7b5

  

  ##### git分支管理

  创建分支

  查看分支的情况，前面带*号的就是当前分支		git branch 

   

  创建分支		git branch 分支名

   

  切换当前分支到指定分支		git checkout 分支名

   

  创建分支并切换到创建的分支		git checkout  -b 分支名

   

  合并某分支的内容到当前分支		git merge 分支名

   

  ##### 删除分支

  git branch -d 分支名git远端库相关

  git remote add origin git://127.0.0.1/abc.git 这样就增加了远程仓库abc。

  git remote remove origin移除远端仓库

   

  将本地仓库内容推送到远端仓库(-u 表示第一次推送master分支的所有内容，后面再推送就不需要-u了)，跟commit的区别在于一个是提交到本地仓库，一个是提交到远程仓库

  git push -u origin master

  从远端库更新内容到本地（相当于svn的update），

  git pull

  tips:如果push的时候，本地和文件和远端文件有冲突，就要先pull、然后手动解决冲突，才能继续push

   

  git记住用户名密码

  push的时候默认每次都需输入GitHub的用户名和密码，在git仓库根目录下.git文件夹的config文件末尾增加如下内容，即可记住用户名密码，无需每次推送都输入了

  [credential]

      	 helper = store
  #### git的全局配置

  ​		第一次完成安装后 告诉git我是谁

  	1. git config -l 查看配置信息

  	2. git config --global -l 查看全局配置信息
   	3. 配置用户名和邮箱

   4. git config --global user.name 'wangguangwei'

   5. git config --global user.email '305263226@qq.com'

      #### 创建本地完成版本控制

      ​	初始化：创建一个git仓库，创建之后就会在当前目录生成一个.git的文件		git init

      

      ​	查看git库的状态，未提交的文件，分为两种，add过已经在缓冲区的，未add过的		git status

      ​					红色工作区 绿色暂存区 看不到证明所有提交到历史区	 git status

      

      ​	添加文件：把文件添加到缓冲区	git add xxxxx

      ​					  添加所有文件到缓冲区（从目前掌握的水平看，和后面加“.”的区别在于，加all可以添加被手动删除					  的文件，而加“.”不行）：

      ​			git add .

      ​			git add --all

      ​	

      

      ​	**提交到历史区**

      ​		提交：提交缓冲区的所有修改到仓库(注意：如果修改了文件但是没有add到缓冲区，也是不会被提交的)

      ​			git commit -m"提交的说明"

      ​			commit可以一次提交缓冲区的所有文件

      

      ​	查看命令历史：查看仓库的操作历史		

      ​		git log	

      ​		git reflog	包含回滚信息

      

      把本地仓库信息提交到远程仓库

      ​	1.简历本地与远程的链接

      	2. git remote -v
       	3. git remote add origin [git远程仓库地址]

      

      

  

  

  

  

  ​	

  ​	

  