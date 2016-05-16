git rest 版本回退
git reset --HEAD^

HEAD指向的版本就是当前版本
git log 查看提交历史，以便查看要回退到过去的哪个版本
git relog 查看命令历史，以便查看要回退到未来的哪个版本

git checkout --file 可以撤销工作区的修改  用版本库代码替换工作区代码

注册github账号
因为本地仓库和远程仓库交互，通过SSH加密，所以要设置SSH key

看在用户主目录下有没有.ssh目录。如果有，就看目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，就直接跳下一步。
id_rsa是私钥。id_rsa.pub是公钥

如果没有

$ ssh-keygen -t rsa -C "email@address.com"

登录github----->Accout settings----->Add SSH Key
填上任意title
Key文本框里粘贴id_rsa.pub文件的内容

点Add Key


git branch  查看当前分支 会列出所有分支，当前分支加上*
git branch <name> 创建分支
git checkout -b <name> 新建并切换分支
git checkout <name> 切换分支

在master分支执行
git merge dev  把dev分支merge到master


git branch -d dev  删除dev分支

git log --graph 查看分支合并图

git remote  查看远程库信息

git remote -v  查看远程库详细信息，会带有git的地址

推送分支  git push origin master      git push origin dev    git push origin snail

git clone只能看到master分支
要在dev分支上开发
git checkout -b dev origin/dev   然后就可以在dev上修改，时不时将dev分支push到远程

多人协作的话，要先pull分支，在本地merge，如果有冲突先解决冲突，然后再push

如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name

git tag <name> 打标签