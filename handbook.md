# 速查手册

- [git-rebase的三个使用场景](git/rebase.md)
- [在提交树上移动(在不同commit和branch间移动)](git/pointer.md)

```shell
git status // 查看本地代码状态
git add files // 添加代码到缓存区
git commit -m '提交内容的备注' // 提交代码到本地仓库
git checkout -b branchName // 不加-b就是普通切换分支
git fetch -p // 同步远端分支状态
git pull -r origin branchName // fetch远端代码到本地，并且以rebase的方式合并代码
git push origin branchName // 更新本地代码到远端
```

