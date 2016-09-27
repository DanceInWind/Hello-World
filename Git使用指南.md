git 使用简介

1.从Git 版本库的初始化
git  clone  git://github.com/someone/some_project.git   some_project 
2.远程仓库相关命令
检出仓库：        $ git clone git://github.com/jquery/jquery.git
查看远程仓库：$ git remote -v
添加远程仓库：$ git remote add [name] [url]
删除远程仓库：$ git remote rm [name]
修改远程仓库：$ git remote set-url --push [name] [newUrl]
拉取远程仓库：$ git pull [remoteName] [localBranchName]
推送远程仓库：$ git push [remoteName] [localBranchName]
3.分支(branch)操作相关命令
查看本地分支：$ git branch
查看远程分支：$ git branch -r
创建本地分支：$ git branch [name] ----注意新分支创建后不会自动切换为当前分支
切换分支：$ git checkout [name]
创建新分支并立即切换到新分支：$ git checkout -b [name]
删除分支：$ git branch -d [name] ---- -d选项只能删除已经参与了合并的分支，对于未有合并的分支是无法删除的。如果想强制删除一个分支，可以使用-D选项
合并分支：$ git merge [name] ----将名称为[name]的分支与当前分支合并
创建远程分支(本地分支push到远程)：$ git push origin [name]
删除远程分支：$ git push origin :heads/[name] 或 $ gitpush origin :[name] 

*创建空的分支：(执行命令之前记得先提交你当前分支的修改，否则会被强制删干净没得后悔)
$git symbolic-ref HEAD refs/heads/[name]
$rm .git/index
$git clean -fdx

4.版本(tag)操作相关命令
查看版本：$ git tag
创建版本：$ git tag [name]
删除版本：$ git tag -d [name]
查看远程版本：$ git tag -r
创建远程版本(本地版本push到远程)：$ git push origin [name]
删除远程版本：$ git push origin :refs/tags/[name]
合并远程仓库的tag到本地：$ git pull origin --tags
上传本地tag到远程仓库：$ git push origin --tags
创建带注释的tag：$ git tag -a [name] -m 'yourMessage'

5.添加忽略
根目录下修改
.gitignore
删除添加在repo里但是又要ignore的文件
After editing .gitignore to match the ignored files, you can do "git ls-files -ci --exclude-standard" to see the files that are included in the exclude lists; you can then do "git ls-files -ci --exclude-standard -z | xargs -0 git rm --cached" to remove them from the repository (without deleting them from disk).


参考资料：
http://blog.csdn.net/ithomer/article/details/7529022
http://gitref.org/zh/remotes/
http://backlogtool.com/git-guide/cn/stepup/stepup2_4.html
http://zensheno.blog.51cto.com/2712776/490748
http://stackoverflow.com/questions/7527982/applying-gitignore-to-committed-files

