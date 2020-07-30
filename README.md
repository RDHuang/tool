# window生成.ssh公钥

  首先查看电脑中是否已经存在此文件

> 目录一般都在 C:\Users\Administrator\.ssh
  若存在，复制此目录下 id_rsa.pub 文件的内容到github or gitee上面添加公钥就好了

如果没有此文件,可以使用如下命令来生成sshkey

```
  ssh-keygen -t rsa -C "your eamil"
```

*按照提示完成三次回车，即可生成ssh key*

> 一种通过查找文件目录复制key添加公钥

```
C:\Users\Administrator\.ssh\id_rsa.pub
```

> 一种使用命令拿到
```
cat ~/.ssh/id_rsa.pub
```

# 添加、修改、删除、查看本地git的用户名和邮箱

1. 添加

```git
git config --global user.name "yourName"
git config --global user.email "your@email.com"
```

2. 修改

* 覆盖

```git
git config --global user.name "yourName"
git config --global user.email "your@email.com"
```

* 替换

```git
git config --global --replace-all user.name "yourName"
git config --global --replace-all user.email "your@email.com"
```

3. 删除

```git
git config --global --unset user.name "yourName"
git config --global --unset user.email "your@email.com"
```

4. 查看

* 查看所有
```git
git config --list
```

* 查看指定信息

```git
git config user.name
git config user.email
```


