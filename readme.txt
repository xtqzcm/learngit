Git is a version control system.
Git is free software.


...learning tracking...

BASIC 
1>
	1.create a git repository
	2.git init
	3.git add <file>
	4.git commit -m "description"
	
2>
	1.git status       								查看工作区状态，看有没有修改)
	2.git diff <file>  								(查看修改内容)
	
3>
	1.git log										(check the log)
	2.git log --pretty=oneline						(simplifie the output,可以显示版本号)
	3.git reset --hard HEAD^						(版本回退，当前版本为HEAD，
													前一个为HEAD^,前一百个可以写成HEAD~100)
	4.git reset --hard commit_id  					(撤销版本回退)
	5.git reflog									(查找被回退，已经不见了的版本的版本号)
	
4>
	about stage (暂存区)
	git add <file>           						add to the stage
	git commit 				 						from stage add to the branch
	
									/stage 暂存区
				工作区 ---  版本库 
									\branch

5>
	unless has been added to the stage, it wouldn't be able to be committed
	
	cat <file>										compare the two file

6>
	git checkout -- <file>							撤销修改
	git reset HEAD <file>							撤销已经add到暂存区但是还没commit的文件
	
7>
	rm <file>										删除文件
	git rm <file> 和 git commit						从版本库删除
	git checkout -- test.txt						删错了一键还原
	
	
	
REMOTE REPOSOTORY
1>
	git remote add origin git@sever-name:path/repo_name.git		
			eg: git remote add origin git@github.com:xtqzcm/learngit.git
	git push -u origin master						第一次推送 master 分支时，加上了-u 参数，
											Git 不但会把本地的 master 分支内容推送的远程新的
											master分支，还会把本地的 master 分支和远程的master
											分支关联起来在以后的推送或者拉取时就可以简化命令。
	git push origin master							把master分支最新修改推送到github
	
2>
	git clone git@sever-name:path/repo_name.git		克隆一个远程仓库过来
	
	
ADD NEW BRANCH
	git checkout -b branch-name						创建并切换到一个branch
		等同于 git branch branch-name 和 git checkout branch-name 
	git branch										列出目前所有branch
	git checkout branch-name						切换到某个branch
	git merge										切回master后可以将branch和master合并
	git branch -d branch-name						删除branch