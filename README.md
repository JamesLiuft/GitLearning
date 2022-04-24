# GitLearning
some git commands record

### 一、基础操作
[1. 看当前work tree中的状态 ](#1)

[2. 查看提交日志 ](#2)

[3. 从远端server恢复文件 ](#3)

[4. 添加文件由git管理 ](#4)

[5. 提交变更](#5)

<p id="1"></p>



#### 1.查看当前work tree中的状态
	git status
- 举堆栗子^_^
1. 比如我查看这个仓库的状态现在是这样的。
```$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
```
&nbsp;&nbsp;&nbsp;&nbsp;神马叫```changes not staged for commit```呢？意思就是可以<a href='https://fanyi.baidu.com/?aldtype=23#en/zh/changes%20not%20staged%20for%20commit' >百度翻译一下</a>就是有更改没有提交。如何提交就按照括弧里的搞就行啦。去看```git add```第一个栗子吧

2. 待定
<p id="2"></p>

#### 2.查看提交日志
	git log   
- 举堆栗子^_^
1. 待定
2. 待定

<p id="3"></p>

#### 3.从远端server恢复文件
	git restore filepath
- 举堆栗子^_^
1. 待定
2. 待定

<p id="4"></p>

#### 4.添加文件由git管理（原文直译：将文件内容添加到索引）
	git add 
- 举堆栗子^_^
1. 这个标题叫啥呢，不会起，反正就是我操作了下```git add README.md```就这样啦。
```James@JAMES_PC MINGW64 /f/00OpenSource/MyRespo/GitLearning (main)
$ git add README.md

James@JAMES_PC MINGW64 /f/00OpenSource/MyRespo/GitLearning (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md


James@JAMES_PC MINGW64 /f/00OpenSource/MyRespo/GitLearning (main)
```
其实这个的意思就是按照原文直译的意思添加到索引后的情况：git对待这个文件的状态由原来的*not staged*  变成了 *will be committed*。接下来可以执行```git commit```啦

2. 待定

<p id="5"></p>

#### 5.提交变更
	git commit
- 举堆栗子^_^
1. Hi，add以后我执行commit啦！这里commit以后要写提交日志，比如：做了哪些修改，解决了哪些bug，为什么这样操作等等。不要觉得我这个测试log写得太简单而提issue啥的，提了我也给你删了，我是仓库管理员，我有绝对的权力。好啦，多哔哔了也没用了，又菜又能说就是我~~~下一步进行push吧

```
James@JAMES_PC MINGW64 /f/00OpenSource/MyRespo/GitLearning (main)
$ git commit
[main 0495a48] first commit log:after add and then commit
                                                          1 file changed, 42 insertions(+)

James@JAMES_PC MINGW64 /f/00OpenSource/MyRespo/GitLearning (main)
$
```

2. 待定
#### 将变更同步到远端仓库（原始帮助直译：git push-更新远程引用以及相关对象）
	git push
- 举堆栗子^_^
1. 来到第一天的终点了，到达这里就下班溜了溜了。
```
James@JAMES_PC MINGW64 /f/00OpenSource/MyRespo/GitLearning (main)
$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 966 bytes | 966.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/JamesLiuft/GitLearning.git
   b1e1805..0495a48  main -> main
```
这是提交后的情况，提交完就同步到远程仓库啦。不要以为commit以后才是重点呀~~

2. 待定

### 二、如何从原始fork的仓库的修改同步到自己仓库

#### 1.关联原仓库地址

```
git remote add 	
usage: git remote add [<options>] <name> <url>

    -f, --fetch           fetch the remote branches
    --tags                import all tags and associated objects when fetching
                          or do not fetch any tag at all (--no-tags)
    -t, --track <branch>  branch(es) to track
    -m, --master <branch>
                          master branch
    --mirror[=(push|fetch)]
                          set up remote as a mirror to push to or fetch from
```
#### 2.以Spring Framework为例，我之前已经fork了原始的仓库到我自己的github里，使用```git remote -v```查看是否存在原始仓库（git remote-管理一组跟踪的存储库）
```
$ git remote -v
origin  https://github.com/JamesLiuft/spring-framework.git (fetch)
origin  https://github.com/JamesLiuft/spring-framework.git (push)
```
#### 3. 添加上游仓库后查看
```
$ git remote add upstream https://github.com/spring-projects/spring-framework.git

James@JAMES_PC MINGW64 /f/00OpenSource/MyRespo/spring-framework (5.3.x)
$ git remote -v
origin  https://github.com/JamesLiuft/spring-framework.git (fetch)
origin  https://github.com/JamesLiuft/spring-framework.git (push)
upstream        https://github.com/spring-projects/spring-framework.git (fetch)
upstream        https://github.com/spring-projects/spring-framework.git (push)
```
#### 4. 更新上游仓库相关的资源 ```git fetch```
```
$ git fetch upstream
remote: Enumerating objects: 5238, done.
remote: Counting objects: 100% (1776/1776), done.
remote: Total 5238 (delta 1776), reused 1776 (delta 1776), pack-reused 3462 eceiving objects: 100% (5238/5238), 1.12 MiBReceiving objects: 100% (5238/5238), 1.17 MiB | 371.00 KiB/s, done.

Resolving deltas: 100% (2415/2415), completed with 918 local objects.
From https://github.com/spring-projects/spring-framework
 * [new branch]            3.0.x        -> upstream/3.0.x
 * [new branch]            3.1.x        -> upstream/3.1.x
 * [new branch]            3.2.x        -> upstream/3.2.x
 * [new branch]            4.0.x        -> upstream/4.0.x
 * [new branch]            4.1.x        -> upstream/4.1.x
 * [new branch]            4.2.x        -> upstream/4.2.x
 * [new branch]            4.3.x        -> upstream/4.3.x
 * [new branch]            5.0.x        -> upstream/5.0.x
 * [new branch]            5.1.x        -> upstream/5.1.x
 * [new branch]            5.2.x        -> upstream/5.2.x
 * [new branch]            5.3.x        -> upstream/5.3.x
 * [new branch]            beanbuilder  -> upstream/beanbuilder
 * [new branch]            conversation -> upstream/conversation
 * [new branch]            gh-pages     -> upstream/gh-pages
 * [new branch]            main         -> upstream/main

```

#### 5. 网页同步方式
 
<a href="https://github.com/JamesLiuft/GitLearning/blob/main/Pictures/fetch_upstream.png">点个按钮就可以</a>


#### 6. 从upstream进行分支同步&冲突处理

1. 通过fetch_upstream并处理<a href="https://github.com/JamesLiuft/GitLearning/blob/main/Pictures/pull_request_deal.png">pull request</a>后，
``` 
git pull https://github.com/spring-projects/spring-framework.git 5.3.x
git checkout 5.3.x
git merge --no-ff spring-projects-5.3.x
git push origin 5.3.x
```




























