# 前端常用工具命令

## window生成.ssh公钥

  首先查看电脑中是否已经存在此文件

> 目录一般都在 C:/Users/Administrator/.ssh

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

## 添加、修改、删除、查看本地git的用户名和邮箱

1. 添加

```git
git config --global user.name "yourName"
git config --global user.email "your@email.com"
```

2. 修改

> 覆盖

```git
git config --global user.name "yourName"
git config --global user.email "your@email.com"
```

> 替换

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

> 查看所有
```git
git config --list
```

> 查看指定信息

```git
git config user.name
git config user.email
```

## vsCode常用插件

1. Auto Close Tag （自动闭合html/xml标签）

2. Auto Rename Tag （自动完成另一侧标签的同步修改）

3. Bracket Pair Colorizer (给括号加上不同的颜色，便于区分不同的区块)

4. Debugger for Chrome （映射vscode上的断点到chrome上，方便调试）

5. ESLint （js语法纠错，可以自定义配置。较复杂）

6. GitLens （方便查看git的日志）

7. HTML CSS Support （智能提示css类型以及id）

8. HTML Snippets （智能提示html标签，以及标签含Markdown Preview Enhanced义）

9. JavaScript(ES6) code snippets （es6语法智能提示，以及快速输入）

10. Markdown Preview Enhanced （实时预览markdown,快捷键打开 ctrl + k  v）

11. markdownlint （markdown语法纠错）

12. Path Intellisense （自动提示文件路径，支持各种快速引入文件）

13. Vetur （vue多功能集成插件---语法高亮，智能提示，错误提示，格式化，自动补全等）

14. filesize （在左下角显示文件大小）

15. Npm Intellisense（rquire时的包提示，node必备）

16. open in browser（支持快捷键与鼠标右键快速在浏览器中打开html文件）

17. Dracula Official （可骚气的主题，吸血鬼）

## VUE项目 使用vscode 相关配置

**在根目录创建 .prettierrc 文件**
> 在里面添加如下代码:
```
{
  "semi": false,
  "singleQuote": true
}
```
*tip: 可以实现使用vscode编辑代码的时候格式化,去除末尾分号*
	
**在根目录创建 .editorconfig 文件**
> 在里面添加如下代码:
```
indent_style = space
indent_size = 2
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true
```
*可以实现统一文件缩进为两格*

## VUE项目配置文件

**.env文件为Vue全局环境变量**

* 首先文件的名字必须是固定格式
  > .env 全局默认配置文件, 不论在什么环境下都会执行 (但权重也是最低的)
  > .env.development 开发环境下的配置文件, 在yarn serve时会执行,会替换.env中相同名称变量的值
  > .env.production 生产环境下的配置文件,在yarn build时会执行,会替换.env中相同名称变量的值

* 文件内容

**属性名必须已 VUE_APP_ 开头**
* .env 文件
```
NODE_ENV=production
VUE_APP_PREVIEW=false
# 正式服务器地址
VUE_APP_BASEURL=https://xxx.com
```
*这里注释代码需要用\#*

* .env.development 文件
```
# 本地调试地址
VUE_APP_BASEURL=https://192.168.0.1:8080
```

**获取全局环境变量**

```js
console.log(process.env) // 获取所有全局环境变量对象,在任何地方都可以使用
// 当运行yarn serve 时
console.log(process.env.VUE_APP_BASEURL)  // 打印结果为 https://192.168.0.1:8080
// 当运行yarn build 时
console.log(process.env.VUE_APP_BASEURL)  // 打印结果为 https://xxx.com
```