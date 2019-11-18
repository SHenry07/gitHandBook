# Bisect二分法--快速定位bug

目的:找到一个引入bug的提交 

解决方法:

- 通过一个逐步弃之的过程，找到一个已知的good提交和bug提交
- 开始修订,比对两次提交的差异

## Bisect sample workflow

1. 开始二分
2. 确定bug (通常是上一次提交)
3. 确定已知的正常运行的版本 (commit/分支)
4. 运行代码 看看bug是否依旧存在
5. 告诉bisect 结果
6. 重复以上步骤,直到确定BUG提交(offending commit)

---------

# 演示

## 准备环境

```shell
  mkdir bisect-ex
  cd bisect-ex
  touch index.html
  git add -A
  git commit -m "starting out"
  vi index.html
  # Add all good
  git add -A
  git commit -m "second commit"
  vi index.html
  # Add all good 2
  git add -A
  git commit -m "third commit"
  vi index.html
  # Add all good 3
  git add -A
  git commit -m "fourth commit"
  vi index.html
  # This looks bad
  git add -A
  git commit -m "fifth commit"
  vi index.html
  # Really bad
  git add -A
  git commit -m "sixth commit"
  vi index.html
  # again just bad
  git add -A
  git commit -m "seventh commit"
```

## 开始

```shell
  git bisect start
  # Test your code
  git bisect bad
  git bisect next
  # Say yes to the warning
  # Test
  git bisect good
  # Test
  git bisect bad
  # Test
  git bisect good
  # done
  git bisect reset
```