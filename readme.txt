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
	
////////////////////////////////////////////////////////////////////////////////	
Git常用操作命令收集：
1) 远程仓库相关命令
检出仓库：$ git clone git://github.com/jquery/jquery.git
查看远程仓库：$ git remote -v
添加远程仓库：$ git remote add [name] [url]
删除远程仓库：$ git remote rm [name]
修改远程仓库：$ git remote set-url --push[name][newUrl]
拉取远程仓库：$ git pull [remoteName] [localBranchName]
推送远程仓库：$ git push [remoteName] [localBranchName]
 
2）分支(branch)操作相关命令
查看本地分支：$ git branch
查看远程分支：$ git branch -r
创建本地分支：$ git branch [name] ----注意新分支创建后不会自动切换为当前分支
切换分支：$ git checkout [name]
创建新分支并立即切换到新分支：$ git checkout -b [name]
删除分支：$ git branch -d [name] ---- -d选项只能删除已经参与了合并的分支，对于未有合并的分支是无法删除的。如果想强制删除一个分支，可以使用-D选项
合并分支：$ git merge [name] ----将名称为[name]的分支与当前分支合并
创建远程分支(本地分支push到远程)：$ git push origin [name]
删除远程分支：$ git push origin :heads/[name]
我从master分支创建了一个issue5560分支，做了一些修改后，使用git push origin master提交，但是显示的结果却是'Everything up-to-date'，发生问题的原因是git push origin master 在没有track远程分支的本地分支中默认提交的master分支，因为master分支默认指向了origin master 分支，这里要使用git push origin issue5560：master 就可以把issue5560推送到远程的master分支了。
    如果想把本地的某个分支test提交到远程仓库，并作为远程仓库的master分支，或者作为另外一个名叫test的分支，那么可以这么做。

$ git push origin test:master         // 提交本地test分支作为远程的master分支 //好像只写这一句，远程的github就会自动创建一个test分支
$ git push origin test:test              // 提交本地test分支作为远程的test分支

如果想删除远程的分支呢？类似于上面，如果:左边的分支为空，那么将删除:右边的远程的分支。

$ git push origin :test              // 刚提交到远程的test将被删除，但是本地还会保存的，不用担心
3）版本(tag)操作相关命令
查看版本：$ git tag
创建版本：$ git tag [name]
删除版本：$ git tag -d [name]
查看远程版本：$ git tag -r
创建远程版本(本地版本push到远程)：$ git push origin [name]
删除远程版本：$ git push origin :refs/tags/[name]
 
4) 子模块(submodule)相关操作命令
添加子模块：$ git submodule add [url] [path]
如：$ git submodule add git://github.com/soberh/ui-libs.git src/main/webapp/ui-libs
初始化子模块：$ git submodule init ----只在首次检出仓库时运行一次就行
更新子模块：$ git submodule update ----每次更新或切换分支后都需要运行一下
删除子模块：（分4步走哦）
1)$ git rm --cached [path]
2) 编辑“.gitmodules”文件，将子模块的相关配置节点删除掉
3) 编辑“.git/config”文件，将子模块的相关配置节点删除掉
4) 手动删除子模块残留的目录
 
5）忽略一些文件、文件夹不提交
在仓库根目录下创建名称为“.gitignore”的文件，写入不需要的文件夹名或文件，每个元素占一行即可，如
target
bin
*.db
/////////////////////////////////////////////////////////////////////////////////////////////	
	
	
ADD NEW BRANCH
	git checkout -b branch-name						创建并切换到一个branch
		等同于 git branch branch-name 和 git checkout branch-name 
	git branch										列出目前所有branch
	git checkout branch-name						切换到某个branch
	git merge										切回master后可以将branch和master合并
	git branch -d branch-name						删除branch
	git log --graph									可以看到分支合并图
git@github.com:RoboMaster/DevelopmentBoard-Examples.git
