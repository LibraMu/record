Git 指令 ( 逐步完善 )

基本流程

	// 获取SSH Key 
	ssh-keygen -t rsa -C "自己邮箱@"

	// 设置自己用户名和邮箱
	git config --global user.name "Your Name"
	git config --global user.email "email@example.com"

	// 创建版本库
	git init 

	// 文件添加和提交到仓库
	git add 文件
	git commit -m ' 说明 '

	// 文件查询更改内容(文件放进暂存区add前查询)
	git diff

	// 添加仓库 git@github.... 自己github仓库地址
	git remote add origin git@github.com:michaelliao/learngit.git
	
	// 主分支推送到远程库 远程库默认origin 当前分支 master 第一次推送加 -u 后续可省略
	git push -u origin master

	// 获取远程库分支，更新本地库
	git pull origin master

	// 远程库克隆 ( 其他文件夹使用 )
	git clone git@github.com:michaelliao/gitskills.git(远程库地址)

时光机

	// 版本回退
		// 提交的历史记录 --pretty=oneline 输出一行
		git log [--pretty=oneline]

		// 回退版本 HEAD表示当前版本 ^上个版本
		git reset --hard HEAD^

		// 未来版本
		git reset --hard 版本号333333

		// 全部记录 ( 不知道未来版本ID )
		git reflog
	
	// 暂存区和工作区
		// git add 文件先存储在暂存区
		// git commit 将暂存区中所有文件全部提交
	
	// 撤销修改
		git checkout --file文件
		// 撤销两种情况
			1. 修改后没有放进暂存区，撤销后和版本库一样
			2. 放进暂存区又修改，撤销回到暂存区状态
			总之，撤销让文件回到最近的commit或add状态
	
	// 删除文件
		// 从版本库删除文件
		git rm 文件
		git commit

		// 删错了,版本库一键还原
		git checkout -- 文件 

远程仓库

	// 添加仓库 git@github.... 自己github仓库地址
	git remote add origin git@github.com:michaelliao/learngit.git
	
	// 远程库信息 -v 显示更详细信息
	git remote [-v]

	// 主分支推送到远程库 远程库默认origin 当前分支 master 第一次推送加 -u 后续可省略
	git push -u origin master

	// 其他分支推送
	git push origin <name>

	// 远程库克隆 
	git clone git@github.com:michaelliao/gitskills.git(远程库地址)

	// 获取远程库分支，更新本地库
	git pull origin master

	// 删除远程分支
	git push origin --delete <branch-name>

	// 远程库重命名
	git remote rename <old-name> <new-name>

	// 更改远程库地址
	git remote set-url origin <url>

分支管理

	// 查看所有分支 * 指当前 -a表示全部分支包括远程库分支
	git branch [-a]

	// 创建和合并
		// 创建并切换分支
		git checkout -b <name>

		// 创建 切换两步 ==  -b
		git branch <name>
		git checkout <name>

		// 分支合并
		git merge <name>

		// 删除分支
		git branch -d <name>

		// 强制删除分支 (没有与其他分支合并)
		git branch -D <name>
		
		// 查看分支合并图
		git log --graph
	
	// 分支合并
		// 合并分支 --on-ff参数表示禁用Fast forward 可以查看合并历史
		git merge --no-ff -m '描述' <name>
	
	// Bug分支
		// 当前工作现场储藏起来
		git stash

		// 确定某分支修复，创建临时分支修改合并删除

		// 查看之前工作现场
		git stash list
	
		// 恢复工作现场
			1. 恢复现场，不删除存储内容
			git stash drop

			2. 恢复同时删除存储
			git stash pop

		// 根据stashID,恢复指定内容
		git stash apply stash@{0}

	// 分支重命名 ( 如果已经推送远程库,要删除远程库分支 ) 
	git branch -m <old-name> <new-name>







	

