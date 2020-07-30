# window生成.ssh公钥

  首先查看电脑中是否已经存在此文件

> 目录一般都在 C:\Users\Administrator\.ssh
  若存在，复制此目录下 id_rsa.pub 文件的内容到github or gitee上面添加公钥就好了

如果没有此文件,可以使用如下命令来生成sshkey

```
  ssh-keygen -t rsa -C "your eamil"
```

>按照提示完成三次回车，即可生成ssh key

> 一种通过查找文件目录复制key添加公钥

**C:\Users\Administrator\.ssh**

> 一种使用命令拿到
```
cat ~/.ssh/id_rsa.pub
```
> 复制显示出来的sshkey添加公钥

