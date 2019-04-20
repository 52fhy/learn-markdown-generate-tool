
官网： https://docsify.js.org/#/  
代码块：https://github.com/docsifyjs/docsify  

> 依赖 node.js 环境。

### 安装

全局安装：
``` bash
npm i docsify-cli -g
```

### 如何使用

创建并初始化项目：
``` bash
$ mkdir test-docsify
$ cd test-docsify

# init project
$ docsify init ./docs
```

执行完毕，生成 `docs` 目录。里面有3个文件：

- `.nojekyll`：让gitHub不忽略掉以 `_` 打头的文件
- index.html：整个网站的核心文件
- README.md：默认页面

接下来预览一下效果：
``` bash
$ docsify serve docs
```
会在本地运行server服务，我们打开浏览器，输入：http://localhost:3000 即可看到 demo 页面。

项目的目录结构示例：
``` 
.
└── docs
    ├── README.md
    ├── guide.md
    └── zh-cn
        ├── README.md
        └── guide.md
```

实际路由对应关系是：
```
docs/README.md        => http://domain.com
docs/guide.md         => http://domain.com/guide
docs/zh-cn/README.md  => http://domain.com/zh-cn/
docs/zh-cn/guide.md   => http://domain.com/zh-cn/guide
```

### 增加一个页面

我们新增 guide.md 文件作为示例：

``` markdown

## docsify

官网： https://docsify.js.org/#/  
代码块：https://github.com/docsifyjs/docsify  

> 依赖 node.js 环境。

### 安装

全局安装：

npm i docsify-cli -g


### 如何使用

创建并初始化项目：

```

我们启动 server 预览效果：
``` bash
$ docsify serve docs
```
浏览：http://localhost:3000/#/guide  

效果截图：
![](http://img2018.cnblogs.com/blog/663847/201904/663847-20190420232957366-912516600.png)

> server 启动后，我们修改文件保存后，浏览器会实时刷新。

### Sidebar

我们可以给文档增加左侧菜单。菜单文件名是`_sidebar.md`。格式要求示例：

``` markdown

<!-- docs/_sidebar.md -->

* [Home](/)
* [Guide](guide.md)
```

保存后需要修改 index.html 启用左侧菜单：
``` html
window.$docsify = {
	  loadSidebar: true,
	  subMaxLevel: 3,
      name: '',
      repo: ''
    }
```

效果：
![](http://img2018.cnblogs.com/blog/663847/201904/663847-20190420234957125-422911433.png)


### 示例项目

- 快速入门 - docsify
https://docsify.js.org/#/quickstart

- Linux C 编程一站式学习
http://me.52fhy.com/linux-c/#/