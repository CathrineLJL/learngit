Git管理的是修改
安装后初始化设置：
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
创建一个空目录：
$ mkdir learngit 
$ cd learngit 
$ pwd 
/Users/michael/learngit
初始化仓库：
$ git init 
Initialized empty Git repository in /Users/michael/learngit/.git/

工作区-->暂存区-->版本库
常用命令：
git add --新增到暂存区
$ git commit -m "我叫注释"  --新增到分支，忘记写注释自行百度解决方法，不可直接关掉
git status --随时掌握工作区的状态爱
git diff  --查看修改的区别
git log ‐‐pretty=oneline  --记录修改历史（--号后面部分可以简洁呈现修改历史）
git reset --hard HEAD^  --退回到上一个版本（HEAD^可以用版本编号来代替）
git reset HEAD readme.txt  --将暂存区的文件撤销
HEAD^ --上一版本
HEAD^^ --上上个版本
HEAD~n --上n个版本
cat readme.txt --显示文件内容
git checkout --file 可以丢弃工作区的修改，没有--符号就变成新加一个分支，用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。
git reflog  --查看命令历史，以便确定要回到未来的哪个版本。
git rm readme.txt --删除工作区的文件，git commit readme.txt --彻底删除版本库中的
git push origin master --本地推到远程库
关联到github：
a.ssh-keygen -t rsa -C "1062998005@example.com"
b.得到 id_rsa.pub 
c.在github上注册，将id_rsa.pub填入ssh key中
d.找到“Create a new repo”按钮,新建一个名为learngit的库
e.在本地bash输入：git remote add origin git@github.com:CathrineLJL/learngit.git，关联到github上的远程库
f.把本地库的所有内容推送到远程库上：$ git push -u origin master ，以后可以省略“-u”