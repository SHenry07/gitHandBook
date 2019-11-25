  HEAD 指向，可以通过 `cat .git/HEAD` 查看， 如果 HEAD 指向的是一个引用，还可以用 `git symbolic-ref HEAD` 查看它的指向。 

##### 建议的合作方式

1. fork\派生 这个仓库
2. clone\克隆 你复制的仓库到本地
3. 创建属于你的要完成的任务的分支并转换到这个分支
4. 提交这个分支到你的仓库
   5 做pull request\合并请求

> Note **fork** first

```shell
 git clone git@gitlab.com:你的用户名/项目名.git
 cd 项目文件夹
 git branch your_sample_name
 git checkout your_sample_name
 vim samples/your_sample_name.py
 git add samples/your_sample_name.py
 git commit
 git push origin your_sample_name
```

现在你可以到official project \主仓库 创建合并请求了
如何在Github上创建、删除分支、合并到master



试想一下，开发过程中，如果我们频繁的 rebase master 分支，会有什么后果呢？



![img](https://pic3.zhimg.com/80/v2-1ac5872e3517280d83aae4c12cb6e576_hd.jpg)



当你不断 rebase master 的时候，其实你本地的 d 都变成了 d` ，再要和远端 pay 分支保持一致，你的本地分支 commit 记录已经不堪入目了。

- 正式修改,执行命令,`-s` 就是自动加上`Signed-off-by:` 

```bash
$ git commit --amend -s 

client_java git:(63b2cfd) git commit --amend -s
[detached HEAD c46b30e] 1should find method from parent
 Date: Mon Apr 16 18:29:29 2018 +0800
 1 file changed, 4 insertions(+), 1 deletion(-
```