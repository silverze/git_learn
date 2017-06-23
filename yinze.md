# git学习笔记

## 学习任务1的操作:   

1.1 添加新的文件至当前所在的分支中  
	`git add yinze.txt`  

1.2 提交暂存区的修改至本地仓库   
`git commit 然后在弹出的编辑器中写入提交log；或者使用 git commint -m "log info" `    

1.3 将已经提交至本地仓库的修改，push至远程仓库   
`git push -u origin master:master`


## 学习任务2的操作:  



## 学习任务3的操作：
	3.1 修改提交一次有误的log后，撤销并修改该log。  
	`git commit --amend`  
	3.2 同时修改了common.txt 与 yinze.md文件；并已经暂存至暂存区了，提交前撤销对
	common.txt的修改  
	```
	git add *
	git reset HEAD common.txt
	git checkout -- common.txt #该命令比较危险；使用它将会使从上次提交至现在所有的修改都丢失
	```
	3.3 合并之前两次的提交  
	```
	git rebase -i HEAD^^ #进入至log编辑模式，然后使用squash命令（简写's'）
	```  
	使用该命令时，会出现类似如下的编辑信息：  
	```
	pick 40d7386 finish task1
	pick 652969c finish task2
	pick 7b2174b finish task3
	```
	将上述内容修改为如下，并保存退出：  
	```
	pick 40d7386 finish task1
	s 652969c finish task2
	s 7b2174b finish task3
	```
