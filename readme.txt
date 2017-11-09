开始学习使用git版本控制
-使用git init 创建git仓库
-使用git add readme.txt 向git仓库添加文件
-使用git commit -m "log" 提交修改
-准备回溯 git reset --hard HEAD^ (or hash )
-用git reflog查看命令历史，以便确定要回到哪个版本
-改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file
-git checkout其实是用版本库里的版本替换工作区的版本，误删文件时可以使用checkout还原
-使用git remote add origin git@github.com:HankWang95/Hank-Wang-s-study-diary.git 把本地仓库与github远程仓库关联，git push -u origin master把本地仓库推送至远程仓库
