## git的基础命令及操作

`git remote -v`查看远程仓库</br>
运行结果示例</br>
```
origin  https://github.com/gxy2314/test.git (fetch)
origin  https://github.com/gxy2314/test.git (push)
//对于一个本地的仓库，需要通过 git remote add origin 远程地址 这一命令与远程仓库关联方可实现上述结果


```
`git checkout 分支名`切换到某个分支</br>
如果该命令无效，不妨尝试`git pull`后再切换</br>
运行结果示例
```
A       test
branch 'a' set up to track 'origin/a'.
Switched to a new branch 'a'
```
`git status`查看状态</br>
该命令会显示当前处于哪个分支，与哪个分支保持一致</br>
`git branch`查看当前所在分支名称</br>
## 一些组合套路
##### 新建一个分支
`git checkout -b 新分支名`以当前分支为基础新建分支</br>
`git push -u origin 新分支名`推送新建分支时，在远端（也就是GitHub）新建此仓库</br>
##### 交代码
__一定一定一定先pull再开始写!__</br>
`git commit -m "注释内容"`(提交到仓库区) 将暂存区中的所有内容提交到本地仓库。</br>
`git add .`将工作区（Working Directory）中所有被修改、新增的文件添加到暂存区（Staging Area）</br>
`git push`推送</br>
##### 创建一个新仓库，并把本地的代码传上去</br>
`git config user.name "用户名"`</br>
`git config user.email "邮箱"`</br>
`ssh-keygen -t rsa -C "邮箱名"`</br>
这一步记得先在某个目录下创建一个ssh用于承接公钥</br>
复制gitsshkey.pub里的所有内容到GitHub的NEW SSH KEY</br>
```
git init
git add .
// 去除不想上传的文件 git rm --cached <文件名>
git commit -m "备注"
git branch -M 更改本地分支名
git remote add origin 远程地址
git remote set-url origin 远程地址
//这是重设地址
#6
git push -u origin 分支名
//最后一条新分支也可以用

```
