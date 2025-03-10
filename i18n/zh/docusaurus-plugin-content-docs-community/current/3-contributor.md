---
title: 贡献者指南
sidebar_position: 4
description: Apache ShenYu 贡献者指南
author: "xiaoyu"
categories: "Apache ShenYu"
tags: ["Contributor"]
date: 2019-04-09
cover: "/img/architecture/shenyu-framework.png"
---


您可以报告bug，提交一个新的功能增强建议或者直接对以上内容提交改进补丁。

## 提交issue

- 在提交issue之前，请经过充分的搜索，确定该issue不是通过简单的检索即可以解决的问题。
- 查看[issue列表](https://github.com/apache/incubator-shenyu/issues)，确定该issue不是一个重复的问题。
- [新建](https://github.com/apache/incubator-shenyu/issues/new/choose)一个issue并选择您的issue类型。
- 使用一个清晰并有描述性的标题来定义issue。
- 根据模板填写必要信息。
- 在提交issue之后，对该issue分配合适的标签。如：bug，enhancement，discussion等。
- 请对自己提交的issue保持关注，在讨论中进一步提供必要信息。

## 开发流程

**Fork分支到本地**

- 从 ShenYu 的repo上fork一个分支到您自己的repo来开始工作，并设置upstream为 ShenYu 的repo。

* 从你的github仓库克隆代码.

```shell
git clone https://github.com/your-github/incubator-shenyu.git
```

* 设置远程仓库 (为了同步代码) .

```shell
git remote add apache https://github.com/apache/incubator-shenyu.git
```

**选择issue**

- 请在选择您要修改的issue。如果是您新发现的问题或想提供issue中没有的功能增强，请先新建一个issue并设置正确的标签。
- 在选中相关的issue之后，请回复以表明您当前正在这个issue上工作。并在回复的时候为自己设置一个deadline，添加至回复内容中。

**创建分支**

- 切换到fork的master分支，拉取最新代码，创建本次的分支。

```shell
git checkout master
git pull apache master
git checkout -b issueNo
```

**注意** ：PR会按照squash的方式进行merge，如果不创建新分支，本地和远程的提交记录将不能保持同步。

**编码**

- 请您在开发过程中遵循 ShenYu 的 [开发规范](../code-conduct)。并在准备提交pull request之前完成相应的检查。
- 将修改的代码push到fork库的分支上。

```shell
git add 修改代码
git commit -m 'commit log'
git push origin issueNo
```

**提交PR**

- 发送一个pull request到 ShenYu 的master分支。
- 接着导师做CodeReview，然后他会与您讨论一些细节（包括设计，实现，性能等）。当导师对本次修改满意后，会将提交合并到当前开发版本的分支中。
- 最后，恭喜您已经成为了ShenYu的贡献者！

**删除分支**

- 在导师将pull request合并到 ShenYu 的master分支中之后，您就可以将远程的分支（origin/issueNo）及与远程分支（origin/issueNo）关联的本地分支（issueNo）删除。

```shell
git checkout master
git branch -d issueNo
git push origin --delete issueNo
```

**注意**

为了让您的id显示在contributor列表中，别忘了以下设置：

```shell
git config --global user.name "username"
git config --global user.email "username@mail.com"
```

**常见问题**

- 每次Pull Request(PR)后,你需要执行以下操作,否则,之前PR的提交记录会和这次的提交记录混在一起,具体操作流程如下:

```shell
git checkout master
git fetch upstream
git reset --hard upstream/master
git push -f
```
