下面是一个通用模板，各项目组可以根据自己需求进行调整，如前台`<scope>`部分可能没有数据层

但是java后台应该一致，vue前端应该一致，python应该一致

#### 直接下载并安装到本地

```shell
curl https://git.banksteel.com/root/simple-ci-description/raw/master/git/template/git-commit-template-common.txt  > ~/.git-commit-template-common.txt`

git config --global commit.template ~/.git-commit-template-common.txt
```


```
# 提交规则
# 一个commit只做一件事情；若一个commit做了多件事情需要拆分成多个commit
# 严格遵循commit message格式
# 每次只允许提交一个commit，若本地有多个commit等待提交，必须等前面的commit
# 合并进入主版本库并在本地合并完成后才可提交后面的commit

# Revert
#如果这个commit用于撤销前面一次的commit,则必须以revert:开头,后面跟着被撤销的
#commit的Header

# 内容要求
# Type(<scope>): <subject>

# <body>

# <footer>

# Header 部分
# type 字段包含:只允许下面7个标识
#   feat：新功能（feature）
#   fix：修补bug
#   docs：文档（documentation）
#   style： 代码格式格式（不影响代码运行的变动）
#   perf: 提高性能的改变
#   refactor：重构（即不是新增功能，也不是修改bug的代码变动）
#   test：增加测试
#   build: 增加或更新影响构建的步骤/额外的依赖 (example scopes: gulp, broccoli, npm)
#   ci: 更改CI配置文件或者脚本 

# scope用于说明 commit 影响的范围，比如app名字、数据层、控制层、视图层等等(可选)

# subject是 commit 目的的简短描述，不超过50个字符
# * 修改了那个模块/类/函数/文件

# Body 部分是对本次 commit 的详细描述，可以分成多行
# * 为什么要进行这次改变必须要进行
# * 如何解决这个问题的
# * 有没有什么副作用 比如 一个known bug /已知问题/未来需要重构请用
# NOTICE："另起一行标注并说明"

# Footer 部分 
# - 以jira Issue开头用来 链接/关闭 Jira Issue
# - 当前代码与上一个版本不兼容，则以BREAKING CHANGE开头，
# 后面是对变动的描述、以及变动理由和迁移方法


# 英文版详细例子，请看这里
# https://github.com/angular/angular/blob/master/CONTRIBUTING.md
# https://github.com/sparkbox/how_to/tree/master/style/git
# 中文版介绍，请看这里
# http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html
```