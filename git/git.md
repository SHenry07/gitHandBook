- [写在前面](#写在前面)
- [Git基本概念](#Git概念)
    - [工作原理/工作区域](#工作原理/工作区域)
    - [文件分类](#文件分类)
- [Help](#Help!)
- [参考](#Reference)

# 写在前面

Git是一个免费的开源 **分布式版本控制系统**，旨在快速高效地处理从小型到大型项目的所有事务。
![branching model](../images/branches.png)

- 无障碍环境切换
- 基于角色的代码线
- 基于特征的工作流程
- 一次性实验

git在此不多做介绍,我也是Noob.
强烈欢迎[访问](http://git.banksteel.com)体验

# Git概念

![工作原理](../images/gitIntroduction.jpg)

#### 工作原理/工作区域

- Workspace:工作区，执行`git add`命令就把改动提交到了暂存区，执行`git pull`命令将远程仓库的数据拉到当前分支并合并，执行`git checkout [branch-name]`切换分支

- Index:暂存区，执行`git commit`命令就把改动提交到了仓库区（当前分支）

- Repository:仓库区（或本地仓库），执行`git push origin master`提交到远程仓库，执行`git clone` 地址将克隆远程仓库到本地

- Remote:远程仓库，就是类似github，coding等网站所提供的仓库

#### 文件分类

- 未跟踪的文件
以前没有告诉过Git的新文件。
- 工作区域
已修改但未提交的文件。
- 临时区域
已标记为已在下次提交中进行的已修改文件。


# Reference

[git中文](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%85%B3%E4%BA%8E%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6)

[自定义git配置](https://git-scm.com/book/zh/v1/%E8%87%AA%E5%AE%9A%E4%B9%89-Git-%E9%85%8D%E7%BD%AE-Git)

[知乎:利用github和git进行多人协作开发](https://zhuanlan.zhihu.com/p/23478654)

[git rebase的好处](https://www.codercto.com/a/45325.html)

[commit message 和changes log编写指南](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)

[前端工程化的代码规范](https://zhuanlan.zhihu.com/p/71143472?utm_source=wechat_session&utm_medium=social&utm_oi=910223710001184768)

[git入门](https://zhuanlan.zhihu.com/p/78206003?utm_source=ZHShareTargetIDMore&utm_medium=social&utm_oi=910223710001184768)