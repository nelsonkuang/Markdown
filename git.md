## Git 常用命令
### git 一个分支完全替换另一个分支
转自：http://www.oschina.net/question/1993919_224813   
`git push origin develop:master -f `   
把本地的 `develop` 分支强制(`-f`)推送到远程 `master`   
   
但是上面操作，本地的 master 分支还是旧的，通常来说应该在本地做好修改再去 push 到远端，所以推荐如下操作   
   
```
git checkout master // 切换到旧的分支   
git reset --hard develop  // 将本地的旧分支 master 重置成 develop
git push origin master --force // 再推送到远程仓库
```