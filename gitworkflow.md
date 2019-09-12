
[返回目录](home)

# 版本号公约

项目版本号采用 X.Y.Z-ENV的的形式来设置。

其中XYZ的解释如下：

- X代表大版本号，在发生彻底重构的情况下才会更改该版本号。
- Y代表小版本号，在新增功能模块的时候更改该版本号。
- Z代表BUG修复版本号，在修复BUG之后更改该版本号。

ENV的解释如下：

正规的版本发布流程包括Alpha、Beta、RC、GA等流程，为了简化开发流程，我们只选择Java常见的SNAPSHOT、RC、RELEASE环境后缀。

- SNAPSHOT作为预览版本，该版本不稳定，在测试环境中随着dev合并到test分支而发生变化，同时SNAPSHOT也是开发的时候所使用的环境后缀。
- RC(Release　Candidate)作为预发布版本，该版本只做BUG修复，不做任何新功能添加，如果有多种解决方案需要对比的，则发布多个RC版本进行候选。
- RELEASE/GA(General Availability)正式稳定版，不多解释。



# 开发上线流程

## SNAPSHOT

**SNAPSHOT对应开发和测试环境**

所有开发基于Dev分支按 ***jira的issue/bug号*** 创建新的本地分支进行开发，issue分支自测通过后，按commit合并规则rebase到本地dev分支，提交到远程dev分支提测。

   **提测**操作流程为:
   - 新建合并请求
   - Source Branch选择dev分支，Target Branch选择test分支进行合并代码
   
> 在这一步需要加入sonar对代码质量进行扫描并做Code Review。
    
如果是Java程序，此时的maven版本号为**X.Y.Z-SNAPSHOT**。

## RC

**RC对应预发布环境**

**测试完毕之后流程**：
- 新建合并请求
- Source Branch选择test分支，Target Branch选择pre分支，
- 合并完代码之后，基于pre分支将程序发布到预发布环境由产品经理进行验收

>这一步不需要进行Sonar扫描
 
如果是Java程序，maven版本号为**X.Y.Z-RC**。

通常情况下，RC版本只有一个，如果出现多个RC版本，用RC1、2、3来区分即可。

详细的例子：假设我们开发缓存数据的选型有Redis和MongoDB两种，但是目前不知道哪一种更合适，就可以发布RC1、RC2来区别不同的候选版本，在git中则对应pre-rc1和pre-rc2两个分支供产品来选择具体由哪个版本正式发布到线上，不过当然我们公司一般极少会遇到这种情况。

## RELASE

**RELASE对应线上环境**

**产品经理验收完毕之后流程**:

- 再次新建合并请求
- Source Brance选择pre分支，Target Branch选择master分支
- 合并完代码之后，开始基于master运行上线流程，这里同样不需要Sonar扫描
- 上线完毕之后，如果需要进行公测（或内测）新建tag并给出正式的版本号，同时maven中的版本号也需要做相应的修改为**X.Y.Z-RELEASE**。

# BUG修复流程

BUG修复需要将Y版本号加1

## 一般性BUG修复

一般性BUG修复，是指目前并没有在开发新的功能，那么这个BUG的修复流程与开发流程一致即可，即：dev合并到test合并到pre合并到master最后上线。

## 并发BUG修复

并发BUG修复意思是正在开发新的功能，但是线上出现了BUG需要修复，又不能中断正在开发的功能，这时候需要从master分支拉取fix分支。修复成功之后将fix分支合并到test分支进行测试，后续走正常发布流程即可。

**需要注意的是，BUG修复会影响master分支的版本号，所以BUG修复之后，所有的dev分支都需要发起一次合并请求，将最新的代码合并到当前正在开发的分支中。**

日常维护master分支与fix分支保持代码同步。

## 紧急BUG修复

紧急BUG指的是严重影响线上功能，导致线上无法正常开展下去，需要紧急上线的，则基于master分支拉取新的urgent-fix分支，然后修改代码，由测试人员基于urgent-fix版本进行测试，完毕后不合并到master，也不修改maven版本号，而是直接基于urgent-fix分支打包上线。

等事情解决之后，再根据[并发BUG修复](##并发BUG修复)流程正常迭代版本号。

[上一模块Git介绍](git)

[返回目录](home)

[下一模块Git与jira集成](git-jira)