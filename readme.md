git 指令

基础指令
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

	

	

