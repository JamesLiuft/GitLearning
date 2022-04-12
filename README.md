# GitLearning
some git commands record

#### 查看当前work tree中的状态
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
#### 查看提交日志
	git log   
- 举堆栗子^_^
1. 待定
2. 待定
#### 从远端server恢复文件
	git restore filepath
- 举堆栗子^_^
1. 待定
2. 待定
#### 添加文件由git管理（原文直译：将文件内容添加到索引）
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
#### 提交变更
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