### 一、创建

#### 1,将当前目录编程git可以管理的仓库

```cmd
git init
```

#### 2.新建文本文件

```cmd
touch readme.txt
```

#### 3.将文件添加大暂存区里

```cmd
git add readme.txt
```

#### 4.将文件提交到仓库

```cmd
git commit -m '提交的注释，随便写'
```

#### 5.查看状态

```cmd
git status
```

#### 6.查看修改了哪些内容

```cmd
git diff readme.txt
```

### 二、版本回退

#### 1.查看历史记录

```cmd
git log
```

```cmd
git log --pretty=oneline
```

#### 2.回退到上一个版本

```cmd
git reset --hard HEAD^
```

#### 3.回退到上上个版本

```cmd
git reset --hard HEAD^^
```

#### 4.回退到前100个版本

```cmd
git reset --hard HEAD~100
```

#### 5.查看版本号

```cmd
git reflog
```

#### 6.通过版本号回退

```cmd
git reset --hard 版本号
```

#### 7.撤销对工作区的修改（未commit到仓库的部分）

```cmd
git checkout -- readme.txt
```

#### 8.删除一个文件

```cmd
rm readme.txt
```

在没有commit之前，文件是可以恢复的，采用

```cmd
git checkout -- readme.txt
```

### 三、远程仓库

#### 1.创建SSH key

```cmd
ssh-keygen -t rsa –C "youremail@example.com"
```

在此命令下，可以生成一个私钥和一个公钥，将公钥文件以记事本打开，复制文本到github

#### 2.进入github

```txt
找到ssh and GPG keys,点击New SSH key 将复制的公钥粘贴进去，创建，，，
```

#### 3.创建一个仓库

```text
我们根据GitHub的提示，在本地的testgit仓库下运行命令：
```

```cmd
git remote add origin https://github.com/liudong1234/firstGit.git
```

#### 4.将本地仓库上传及连接

把当前分支master推送的远程

```cmd
git push -u origin master
```

从现在起，只要本地作了提交，就可以通过一下命令

```cmd
git push origin master
```

把本地master分支的最新修改推送到github上了

#### 5.将远程仓库克隆到本地

```cmd
git clone 链接
```

### 四、创建与合并分支

#### 1.创建dev分支

```cmd
git checkout -b dev
```

git checkout 命令加上 –b参数表示创建并切换，相当于如下2条命令

git branch dev

git checkout dev

#### 2.查看当前分支

```cmd
git branch
```

#### 3.切换到master分支

```cmd
git checkout master
```

#### 4.合并分支

```cmd
git merge dev
```

#### 5.删除dev分支

```cmd
git branch -d dev
```

#### 6.隐藏现场

将当前现场隐藏起来，以便于做其他工作，而不用将当前内容commit

```cmd
git stash
```

工作现场还在，Git把stash内容存在某个地方了，但是需要恢复一下，可以使用如下2个方法：

- 恢复

```cmd
git stash apply
```

恢复后，stash内容并不删除，你需要使用命令删除

```cmd
git stash drop
```

- 恢复的同时把stash内容也删除了。

```cmd
git stash pop
```

#### 五、多人协作模式

首先，可以试图用git push origin branch-name推送自己的修改.
如果推送失败，则因为远程分支比你的本地更新早，需要先用git pull试图合并。
如果合并有冲突，则需要解决冲突，并在本地提交。再用git push origin branch-name推送。
