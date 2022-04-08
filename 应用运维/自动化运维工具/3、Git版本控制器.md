[toc]

## 一、作用

* 主要记录文本文件的变化（像代码等），便于回退
* 便于多人协同开发

## 二、安装git工具

```bash
[root@salt-syndic ~]# yum install -y git 
```

### 1、初始化设置

```bash
[root@salt-syndic ~]# git config --global user.name "Martin"
[root@salt-syndic ~]# git config --global user.email "Martin@qq.com"
[root@salt-syndic ~]# git config --global color.ui true
```

## 三、Git常用管理操作

### 1、创建git仓库

```bash
# cd /opt/work
# git init
Initialized empty Git repository in /opt/work/.git/
```

### 2、提交修改

```bash
# git add 文件名称
# git commit -m "说明信息" 文件名称
```

### 3、查看仓库的状态

```bash
[root@salt-syndic work]# git status
# On branch master
nothing to commit, working directory clean
```

### 4、版本回退

```bash
# git reflog
# git reset --hard <版本ID>
```

### 5、删除文件

```bash
# git rm 
# git commit -m "说明信息"
```

### 6、重命名文件

```bash
# git mv 
# git commit -m "说明信息"
```

## 四、暂存区、缓存区

### 1、撤销未提交的修改

*  此时还没有git add

```bash
# git checkout -- <文件名称>
```

### 2、撤销暂存区的修改

* 已经git add
* 先执行 reset
* 再执行  checkout

```bash
# git reset HEAD file02.txt
# git checkout -- file02.txt
```

### 3、撤销工作区的修改

* 直接回滚上一个版本

```bash
# git reset --hard df7e7f7
```

## 五、分支

* 分支之间是互相隔离的

### 1、查看分支

```bash
[root@salt-syndic work]# git branch 
* master
```

### 2、创建、切换分支

```bash
[root@salt-master linux]# git branch AA
[root@salt-master linux]# git branch 
  AA
* master

[root@salt-master linux]# git checkout AA     //切换分支
Switched to branch 'AA'
[root@salt-master linux]# git branch 
* AA
  master
```

### 3、创建分支

```bash
[root@salt-syndic work]# git checkout -b test

[root@salt-syndic work]# git branch 
  master
* test
  update
```

### 4、删除分支

```bash
[root@salt-syndic work]# git branch -d test
```

### 5、合并分支

* **将指定的分支合并到当前分支**

```bash
# git merge <分支名称>
```

