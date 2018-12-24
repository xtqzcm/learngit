Git is a version control system.
Git is free software.


...learning tracking...

1>
	1.create a git repository
	2.git init
	3.git add <file>
	4.git commit -m "description"
	
2>
	1.git status       (查看工作区状态，看有没有修改)
	2.git diff <file>  (查看修改内容)
	
3>
	1.git log					(check the log)
	2.git log --pretty=oneline	(simplifie the output,可以显示版本号)
	3.git reset --hard HEAD^	(版本回退，当前版本为HEAD，
								 前一个为HEAD^,前一百个可以写成HEAD~100)
	4.git reset --hard commit_id  	(撤销版本回退)
	5.git reflog				(查找被回退，已经不见了的版本的版本号)
	
4>
	about stage (暂存区)
	git add <file>           add to the stage
	git commit 				 from stage add to the branch


