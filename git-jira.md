# Related issues 关联的jira上的issue

> 如果commit 信息中有以下信息，会自动关联

1. 只是关联提交或者合并请求

    在commit信息中添加issue ID
```
git commit -m "docs(jira):增加了详细说明" -m "修改了git-jira.md" -m "GEARS-1111'
```

2. 关闭jira问题
- `Resolves PROJECT-1`
- `Closes PROJECT-1`
- `Fixes PROJECT-1`

 `PROJECT-1`就是issue ID形如:`GEARS-11479`
```
git commit -m "docs(jira):增加了详细说明" -m "修改了git-jira.md" -m "Closes GEARS-1111'
```

**以上是命令行的举例方式，IDE中集成的git直接写commit信息就好,commit信息是支持多行的，所以为了有好的阅读感觉，请注意换行**

## 如何获取issue ID

**看图示**

脱敏处理

[上一模块Git工作流](gitworkflow)

[返回目录](home)

[下一模块Git与Sonarqube集成](git-sonar)
