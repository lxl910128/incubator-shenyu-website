---
title: Contributor
sidebar_position: 4
description: Apache ShenYu Contributor's Guide
author: "xiaoyu"
categories: "Apache ShenYu"
tags: ["Contributor"]
date: 2019-04-09
cover: "/img/architecture/shenyu-framework.png"
---


You can report a bug, submit a new function enhancement suggestion, or submit a pull request directly.

## Submit an Issue {#submit-an-issue}

- Before submitting an issue, please go through a comprehensive search to make sure the problem cannot be solved just by searching.
- Check the [Issue List](https://github.com/apache/incubator-shenyu/issues) to make sure the problem is not repeated.
- [Create](https://github.com/apache/incubator-shenyu/issues/new/choose) a new issue and choose the type of issue.
- Define the issue with a clear and descriptive title.
- Fill in necessary information according to the template.
- Choose a label after the issue is created, for example: bug，enhancement，discussion.
- Please pay attention to your issue, you may need to provide more information during discussion.

## Developer Flow {#developer-flow}

**Fork ShenYu repo**

- Fork a `Apache ShenYu` repo to your own repo to work, then setting upstream.

* git clone from your repository.

```shell
git clone https://github.com/your-github/incubator-shenyu.git
```

* set remote repository (To synchronize remote repository updates) .

```shell
git remote add apache https://github.com/apache/incubator-shenyu.git
```

**Choose or Creator Issue**

- Please choose the issue to be edited. If it is a new issue discovered or a new function enhancement to offer, please create an issue and set the right label for it.
- After choosing the relevant issue, please reply with a deadline to indicate that you are working on it.

**Create Branch**

- Switch to forked master branch, pull codes from upstream, then create a new branch.

```shell
git checkout master
git pull apche master
git checkout -b issueNo
```

**Notice** ：We will merge PR using squash, commit log will be different from upstream if you use the old branch.

**Coding**

- Please obey the [Code of Conduct](/en/contribute/code-conduct/) during the process of development and finish the check before submitting the pull request.
- push code to your fork repo.

```shell
git add modified-file-names
git commit -m 'commit log'
git push origin issueNo
```

**Submit Pull Request**

- Send a pull request to the master branch.
- The mentor will do code review before discussing some details (including the design, the implementation and the performance) with you. The request will be merged into the branch of current development version after the edit is well enough.
- At last, congratulate to be an official contributor of ShenYu.

**Delete Branch**

- You can delete the remote branch (origin/issueNo) and the local branch (issueNo) associated with the remote branch (origin/issueNo) after the mentor merged the pull request into the master branch of ShenYu.

```shell
git checkout master
git branch -d issueNo
git push origin --delete issueNo
```

**Notice**:  Please note that in order to show your id in the contributor list, don't forget the configurations below:

```shell
git config --global user.name "username"
git config --global user.email "username@mail.com"
```

**FAQ**

- After each Pull Request (PR), you need to execute the following operations, otherwise, the previous PR commit records will be mixed with this PR commit records. The specific operation process is as follows:

```shell
git checkout master
git fetch upstream
git reset --hard upstream/master
git push -f
```
