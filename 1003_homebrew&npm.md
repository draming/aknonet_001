### 我要Homebrew干啥用

呃，因为，在试图学习python的第一步，安装指引说，在mac上要这样
`brew install python3`

度娘说，Mac 是基于Unix的，可以使用Linux下很多开源软件，但安装过程对于依赖库的手工配置是很辛苦的，于是就有了homebrew。
咱理解就是，homebrew可以帮忙简单快速的安装（下载、编译、安装、配置环境变量等）linux下的开源软件，上面一行命令安装python3，也确实简单快速～

### Homebrew的安装

曾经有小伙伴在我本本上装过homebrew，安装过程就参见[官网](https://brew.sh/index_zh-cn.html)吧。

### Homebrew的使用

- 安装软件
`brew install PKG_NAME`
brew install python3

- 搜索软件
`brew search PKG_NAME`
brew search python3

- 查看软件信息
`brew info PKG_NAME`
brew info python3

- 卸载软件
`brew uninstall PKG_NAME`
brew uninstall python3


----


### npm又是什么鬼

虽然说，npm是node.js安装包管理工具，放在node.js下面比较合适，但是，就是要放在这里，啦啦啦，因为，目前，咱，还，不，会，用。。。

npm是随同node.js一起安装的包管理工具，能解决node.js代码部署上的很多问题，常见的使用场景有以下几种：
- 允许用户从npm服务器下载别人编写的第三方包到本地使用。
- 允许用户从npm服务器下载并安装别人编写的命令行程序到本地使用。
- 允许用户将自己编写的包或命令行程序上传到npm服务器供别人使用。
由于新版的nodejs已经集成了npm，所以之前npm也一并安装好了。


### npm的使用

测试npm安装是否成功`npm -v`，返回版本号
使用npm命令安装模块 `npm install <module name>`
查看所有全局安装的模块 `npm list -g`
查看某个模块的版本号 `npm list <module name>`
更新某个模块 `npm update <module name>`
查找某个模块 `npm search <module name>`
卸载某个模块 `npm uninstall <module name>`



