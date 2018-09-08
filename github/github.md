第一个  
------
就是checkout的问题 我的checkout按理说会回到上一次add或者commit  可是 在我add到暂存区后修改checkout没有反应


第二个  
------
 就是push的问题  至今出现了三次  一次是因为我的本地没有readme  一次是因为我没有add和commit就push  这一次是因为我在hub删除了一个txt 然后本地直接删除 重建了一个md文件 可是一直报错
 #### ok解决了 git pull --rebase origin master


第三个  
---
就是add. 感觉挺好玩 有空看下


第四个  
----
很严重的问题，基本耗完了一个晚上，在我push的时候 因为我在hub直接删除了daily2.txt然后重建了daily2.md 再想pushmd的时候一直在报错各种错  
git push -u origin master
To github.com:justabugg/learn.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:justabugg/learn.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
这是push的时候报的
然后我还尝试clon了一个learn到我的learn里删不掉（明天尝试）

$ git pull
remote: Counting objects: 8, done.
remote: Compressing objects: 100% (8/8), done.
remote: Total 8 (delta 5), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (8/8), done.
From github.com:justabugg/learn
   2a3b0cc..806520b  master     -> origin/master
CONFLICT (rename/delete): daily2.txt deleted in 806520bbd6ab1032601cf22f919ce04d7d8172ef and renamed to daily2.md in HEAD. Version HEAD of daily2.md left in tree.
Automatic merge failed; fix conflicts and then commit the result.
这是pull的时候报的
最后改回了txt然后删了md 重新pull 现在我尝试重新正常的用代码删除txt再添加md


第五个  
-------
关于清除untrack file

第六个  
--------
stash的作用  在例子里说的是手头的dev做了一半没commit，想做个分支修复bug就先stash，可是我直接checkout -b一个bug分支也没事啊 原来的文件add一下不可以么 感觉错过了什么东西


第七个  
-------------
 git pull 以及git merge合并
解答：  git pull将会抓取最新的提交分支到本地 再合并  git merge是从指定的commit合并到当前分支 即GIT PULL=GIE FETCH +GIT MERGE


第八个  解决冲突的方法。


第九个 rebase


