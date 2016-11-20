(1)避免～文件上传  vi .gitignore  添加 # temp file 即可
                                              *~
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
(11)git add	git commit -m ""	git status	git diff	
    git reflog	git checkout -- test.txt		git reset --hard id
    git log --pretty=oneline  		git reset --hard HARD^
(12)git checkout -b dev  //创建dev分支并切换到当前        等价  ：git brance dev	git checkout dev
    git branch //查看分支		git merge dev  //合并dev分支		git branch -d dev    //删除dev		
    git log --graph --pretty=oneline --abbrev-commit  
(13)git merge --no-ff -m "merger with no-ff" dev    //禁用fast forward 模式
	git log --graph --pretty=oneline --abbrev-commit   //科技查看合并效果
(14)git stash   //隐藏当前修改（没有提交），git stash list   //查看隐藏
	git stash pop //恢复隐藏文件
(15)git remote   //要查看远程库的信息		
	git push origin master/dev  //推送分支(注意：可以在另一台电脑（注意要把SSH Key添加到GitHub）或者同一台电脑的另一个目录下克隆)
	git clone git@github.com:......   //抓取分支，默认为master
	git checkout -b dev origin/dev    //在本地建立dev分支，前提是远程有dev
	git branch --set-upstream dev origin/dev   //本地dev和远程dev连接
	git pull //抓取远程最新提交
(16)参与开源项目：在github网站点击fork即可克隆开源项目
