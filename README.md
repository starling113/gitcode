# gitcode
初始化一个Git仓库，使用git init命令。

添加文件到Git仓库，分两步：

	第一步，使用命令git add <file>，注意，可反复多次使用，添加多个文件；

	第二步，使用命令git commit，完成。
	
要随时掌握工作区的状态，使用git status命令。

如果git status告诉你有文件被修改过，用git diff可以查看修改内容。	
	
HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。	
	
	每次修改，如果不add到暂存区，那就不会加入到commit中
	
命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销，这里有两种情况：

一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

总之，就是让这个文件回到最近一次git commit或git add时的状态

git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令
	
小结
又到了小结时间。
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。
场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。	
	
文件已修改，未add到暂存区:
git checkout -- file可还原

文件已修改，并add到暂存区未commit：
git read HEAD file
git checkout -- file可还原	

保存到暂存区的情况，其实可以一条命令搞定：
git reset --hard head	
	
命令git rm用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失最近一次提交后你修改的内容。	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
