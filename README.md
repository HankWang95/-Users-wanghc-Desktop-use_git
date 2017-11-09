开始学习使用git版本控制
- 使用git init 创建git仓库
- 使用git add readme.txt 向git仓库添加文件
- 使用git commit -m "log" 提交修改
- 准备回溯 git reset --hard HEAD^ (or hash )
- 用git reflog查看命令历史，以便确定要回到哪个版本

- 改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file

- git checkout其实是用版本库里的版本替换工作区的版本，误删文件时可以使用checkout还原
- 使用git remote add origin git@github.com:HankWang95/Hank-Wang-s-study-diary.git 把本地仓库与github远程仓库关联，git push -u origin master把本地仓库推送至远程仓库

- 切换分支 git checkout <name>
- 创建+切换分支：git checkout -b <name>
- 合并某分支到当前分支：git merge <name>
- 删除分支：git branch -d <name>

- 合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并

- 修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；
- 当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场。

- 开发一个新feature，最好新建一个分支；
- 如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除。

- 多人协作的工作模式通常是这样：
首先，可以试图用git push origin branch-name推送自己的修改；
如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；
如果合并有冲突，则解决冲突，并在本地提交；
没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！
如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name。

- 使用 git tag -a <tagname> -m "说明" (commit id) 来创建一个标签

- 忽略某些文件时，需要编写.gitignore；
.gitignore文件本身要放到版本库里，并且可以对.gitignore做版本管理

- 配置别名 git config --global alias.last 'log -1' 这样输入 git last == git log -1
也可以直接修改配置文件
仓库的Git配置文件都放在.git/config
- git commit --amend可以修改最近的log信息
