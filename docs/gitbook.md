
# gitbook

官网： https://www.gitbook.com/

> 依赖 node.js 环境。
 
特点：  
1、扩展性非常好，有社区支持。支持插件。  
2、目录需要手动配置。  
3、支持生成html、pdf、epub文件。  

因为 gitbook 扩展性很强，下面仅给出简要教程，详细教程请阅读：https://github.com/52fhy/gitbook-use

### 安装

1、安装 `gitbook` 编辑器：  
https://legacy.gitbook.com/editor/  


2、运行下面的命令进行安装 `gitbook-cli`：
```bash
npm install gitbook-cli -g
```

其中 `gitbook-cli` 是 `gitbook` 的一个命令行工具, 通过它可以在电脑上安装和管理 `gitbook` 的多个版本。

注意：
- `gitbook-cli` 和 `gitbook` 是两个软件
- `gitbook-cli` 会将下载的 `gitbook` 的不同版本放到 `~/.gitbook` 中, 可以通过设置`GITBOOK_DIR`环境变量来指定另外的文件夹

### 如何使用

新建一个项目：
``` $
$ mdkir test_gitbook && cd test_gitbook
```

初始化目录结构：
``` bash
$ gitbook init
```


```
├── README.md
├── SUMMARY.md
```

使用下列命令会运行一个服务器, 通过`http://localhost:4000/`可以预览书籍：

```bash
gitbook serve
```

运行该命令后会在书籍的文件夹中生成一个 `_book` 文件夹, 里面的内容即为生成的 html 文件。
我们可以使用下面命令来生成网页而不开启服务器。

```bash
gitbook build
```

# 目录结构

GitBook 基本的目录结构如下所示
```
├── book.json
├── README.md
├── SUMMARY.md
├── chapter-1/
|   ├── README.md
|   └── something.md
└── chapter-2/
    ├── README.md
    └── something.md
```

- `book.json` 为配置文件
- `README.md` 主页
- `SUMMARY.md` 目录文件

### 目录文件

`SUMMARY.md` 示例：

```  markdown
# Summary
## 基本使用
* [前言](introduction.md)
* [安装](installation.md)
* [命令](commands.md)
* [目录结构](structure.md)
* [配置](settings.md)

## 扩展
* [插件](plugins.md)
* [主题](themes.md)
* [bookjson](bookjson.md)
```

### 配置文件

`book.json` 示例： 
``` js
{
    "title": "Go Web编程",
    "description": "build-web-application-with-golang",
    "author": "谢孟军",
    "output.name": "build-web-application-with-golang-zh",
	"pdf":{
		"fontFamily":"微软雅黑"
	}
}
```

### 命令

**列出gitbook所有的命令**
```bash
gitbook help
```

**输出`gitbook-cli`的帮助信息**
```bash
gitbook --help
```

**生成静态网页并运行服务器**
```bash
gitbook serve
```

**生成静态网页**
```bash
gitbook build
```

**生成pdf**
```bash
gitbook pdf
```

**生成epub**
```bash
gitbook epub
```

**生成时指定gitbook的版本, 本地没有会先下载**
```bash
gitbook build --gitbook=2.0.1
```

**列出本地所有的gitbook版本**
```bash
gitbook ls
```

**列出远程可用的gitbook版本**
```bash
gitbook ls-remote
```

**安装对应的gitbook版本**
```bash
gitbook fetch 标签/版本号
```

**更新到gitbook的最新版本**
```bash
gitbook update
```

**卸载对应的gitbook版本**
```bash
gitbook uninstall 2.0.1
```

**指定log的级别**
```bash
gitbook build --log=debug
```

**输出错误信息**
```bash
gitbook builid --debug
```

> 注：生成pdf、epub需要安装calibre插件，下载链接：https://calibre-ebook.com/download 。Mac 环境需要一个命令 `sudo ln -s /Applications/calibre.app/Contents/MacOS/ebook-convert /usr/local/bin`。

### 常见问题

1、gitbook生成pdf时缺少ebook.css  
找到 `C:\Users\YJC\.gitbook\versions\3.2.3\lib\output\website`，将`copyPluginAssets.js`文件中67行和112行的“confirm: true” 改为：“confirm: false”。

### 示例项目

1、52fhy/gitbook-use: 记录GitBook的一些配置及插件信息  
https://github.com/52fhy/gitbook-use  
2、Introduction · Go Web编程  
http://doc.52fhy.com/build-web-application-with-golang/zh/index.html



