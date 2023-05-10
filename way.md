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

7.撤销对工作区的修改（未commit到仓库的部分）

```cmd
git checkout --readme.txt
```

