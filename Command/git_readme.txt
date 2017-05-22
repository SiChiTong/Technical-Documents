(1)避免～文件上传  vi .gitignore  添加 # temp file 即可
(2)提交命令：git commit -m " "
(3)删除：git rm "your file"
(4)查看历史版本：git reflog 
(5)切换到历史版本：git reset --hard "history address"
(6)轻松地把误删的文件恢复到最新版本:git checkout -- test.txt   其中test.txt为误删的文件。
(7) 删除分支：git branch -d dev
(8) git push // 上传
(9) git pull // 下载 
(10)分支管理： 
        1.创建和切换分支:"git checkout -b dev"   or  "git branch dev"  
                                                    "git checkout dev"
        2.查看分支：git branch
        3.添加和提交：$git --all  
                      $git commit -m "  instrument"
        4.切换到master：git checkout master
        5.合并dev：git merge dev
        6.删除dev：git branch -d dev
(11)git add  	git commit -m ""	git status	 	git diff	
    git reflog	git checkout -- test.txt		git reset --hard id
    git log --pretty=oneline  		git reset --hard HARD^
(12)git checkout -b dev  //创建dev分支并切换到当前        等价  ：git brance dev	git checkout dev
    git branch //查看分支		git merge dev  //合并dev分支		git branch -d dev    //删除dev		
    git log --graph --pretty=oneline --abbrev-commit  //合并的分支，可以查看合并曲线  
(13)git merge --no-ff -m "merger with no-ff" dev    //禁用fast forward 模式
(14)git stash   //隐藏当前修改（没有提交），git stash list   //查看隐藏
	git stash pop //恢复隐藏文件
(15)git remote   //要查看远程库的信息		
	git push origin master/dev  //推送分支(注意：可以在另一台电脑（注意要把SSH Key添加到GitHub）或者同一台电脑的另一个目录下克隆)
	git clone git@github.com:......   //抓取分支，默认为master
	git checkout -b dev origin/dev    //在本地建立dev分支，前提是远程有dev
	git branch --set-upstream dev origin/dev   //本地dev和远程dev连接
	git pull //抓取远程最新提交
(16)参与开源项目：在github网站点击fork即可克隆开源项目

(17)
多人协作的工作模式通常是这样：

>首先，可以试图用git push origin branch-name推送自己的修改；

>如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；

>如果合并有冲突，则解决冲突，并在本地提交；

>没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！

>如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name。

>这就是多人协作的工作模式，一旦熟悉了，就非常简单
(18)

配置文件介绍
Git的配置文件分为系统级别(system)、用户级别(global)和仓库级别三个，详细内容可参考man git-config。

/etc/gitconfig
系统级别的git配置文件，对系统上的所有用户和所有代码仓库都有效，可被用户级别(~/.gitconfig)和仓库级别(.git/config)的配置文件覆盖。
使用git config --system ... 命令可以修改该配置。

~/.gitconfig
用户级别的git配置文件，对该用户的所有代码仓库都有效，可被仓库级别的配置文件(.git/config)覆盖。
使用git config --global ... 命令可以直接修改该配置。

$repo/.git/config
仓库级别的git配置文件，仅对当前代码仓库($repo)有效，但是可覆盖定义在/etc/gitconfig和~/.gitconfig里的配置。
git config ... 命令默认修改此配置文件，如果想使用另外的路径存储配置文件可以为git confi命令使用'-f/--file'选项。


如下是我在~/.gitconfig中的配置文件
  1 [user]
  2     email = gongwenbotarsbot@gmail.com
  3     name = gongwenbo
  4 [alias]
  5     co=checkout
  6     ci=commit
  7     br=branch
  8     st=status
  9     lg=log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit










