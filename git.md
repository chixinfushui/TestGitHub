1、git 客户端设置用户名
   >git config --global user.name 'chixinfushui'  
   >2、git 设置用户名邮箱
   >git config --global user.email '364105294@qq.com'

设置在github仓库主页显示谁提交了该文件

查看设置
>git config --list

在文件内初始化仓库：
>git init

git提交本地仓库
>git add filename
>git commit -m 'something'

git 克隆
>git clone 仓库地址

本地仓库同步到远程仓库
>git push


提交出错，配置./git/config
url = https://用户名:密码@github.





尚硅谷

本地托管代码库

- gitlab

远程托管代码库

- github
- 码云



git本地操作

1. git init

2. 签名   ->  用户名， email    用于区分不同开发人员的身份。   这里的签名和登录远程库没关系。

   git config --global user.name 'chixinfushui'  
   git 设置用户名邮箱
   git config --global user.email '364105294@qq.com'

   级别  

   - 项目级别

     git config

     - 保存在./git/config    [user]

   - 系统用户级别

     git config --global

     - 保存在  ~/.gitconfig   [user]

     优先级就近原则。项目级别优先于系统用户级别。二者都没有不允许。

3. git status

   git add a.txt       加入缓存区

   git rm -- cached a.txt       从缓存区删去文件

   git commit a.txt           ->   vim   

   或者 git commit -m '...'

4. git log       空格向下翻页，b向上翻页 q退出

   - HEAD 当前版本指针
   - git log --pretty=oneline   简洁版log
   - git log --oneline   简洁版log
   - git reflog    显示各个版本距离当前版本距离

5. 版本前进后退，

   1） 基于索引值（推荐）

   - git reflog
   - git reset --hard 索引值

   2）基于^符号

   - 只能往后退 

     git reset --hard HEAD^    往后退1个版本，

     git reset --hard HEAD^^  往后退2个版本

   3）基于~符号

   - 只能往后退

     ​git reset --hard HEAD~3   往后退3个版本

6. git help reset 

   查看帮助文档

   --soft   仅仅在本地库移动 HEAD 指针

   --mixed     在本地库移动 HEAD指针， 重置暂存去

   --hard    在本地库移动HEAD指针，重置暂存区，重置工作区

7. 文件差异

   git diff a.txt       工作区与暂存区比较

   git diff HEAD^ a.txt     与上一个版本比较

8. 分支

   git branch -v        分支情况

   - 创建分支      git branch hot_fix

   - 分支切换      git checkout  hot_fix                  hot_fix   为分支名

   - 合并分支      

     1）首先要站在接收修改的分支上，例如主分支（增加新内容）

     2）执行merge           git merge hot_fix

     3)冲突，git add 

     ​              git commit       （不带文件名）