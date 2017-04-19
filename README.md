# doc
## 课程目标

## 01-Nodejs-初识Nodejs
1、什么是Node
> Node 是一种建立在Ghrome V8引擎之上的基于事件驱动和非阻塞I/O模型的JavaScript运行时<br>
> Node 平台使用的开发语言是JavaScript <br>
> 平台提供了操作系统底层的API，方便做服务器端编程,具体包括文件操作、进程操作、通信操作等系统模块
2、Node的特性是什么
> 事件驱动，非阻塞I/O模型
3、Node的应用场景
- <b>最主要的：Node可以充当一个web服务器</b>
    + 无论是网站后台服务器
    + 还是游戏后台服务器
- 具有复杂逻辑的网站
    + 动态网站
        * 把之前写的静态页面给动态化（数据的动态展示）
        * Node充当的就是一个后台web服务器
- 多人游戏、实时系统、联网软件和具有上千个并发用户的应用程序
- 实时多人游戏后台服务器
- 基于Web的聊天客户端
- 单页面浏览器应用程序
- WebSocket服务器
- 命令行工具
- 带有图形界面的本地应用程序
-
- <b>不适合 CUP 密集型应用</b>
4、谁在用Node
- 淘宝
- 天猫所有的页面都是使用Node进行渲染
- 京东
- 百度等
## 02-Nodejs-开发环境安装配置

1、使用安装包的方式 (nvm)
2、通过nvm 安装和管理Node
1. 在C盘新建一个文件夹 dev
2. 在dev下新建两个文件夹，一个为nodejs，一个为nvm
3. 将解压文件解压到nvm文件夹下
4. 进去nvm文件夹下，以管理员方式运行 install.cmd，会生成settings.txt
5. 点击settings.txt，更改路径
6. 配置环境变量NVM_HOME、NVM_SYMLINK，
7. 将上面配置好的变量添加到环境变量中的path，%NVM_HOME%;%NVM_SYMLINK%; 注意";"
8. 测试是否配置成功 nvm v;

3、nvm 常用命令

> 1. nvm install latest  64/32/all --- 安装最新的版本,后面参数是电脑的位数
> 2. nvm install 6.9.1  --- 后面参数是安装的版本号
> 3. nvm use xxx  --- 切换node版本号
> 4. nvm arch  --- 查看或者设置平台类型
> 5. nvm install  --- 安装node
> 6. nvm list --- 查看安装了哪几个版本的node
> 7. nvm version  --- 查看nvm版本号
## 03-Nodejs-开发环境安装配置注意事项
1、注意事项：
1. 卸载掉之前安装的版本，
2. 运行 install.cmd，没有生成settings.txt，在其他地方拷贝然后更改设置
3. 主要一定要添加到环境变量中
2、镜像安装
- 什么是镜像：
    +  镜像：副本、拷贝,一个磁盘上的数据在另一个磁盘上存在一个完全相同的副本即为镜像
    +  [淘宝NodeJS镜像：https://npm.taobao.org/mirrors/node](https://npm.taobao.org/mirrors/node)
    +  [淘宝npm镜像：https://npm.taobao.org/mirrors/npm/](https://npm.taobao.org/mirrors/npm/)

3、手动配置path环境变量


## 04-Nodejs-终端基本使用

1、什么是终端

> 终端也叫控制台，有人也叫bash(在Linux中)，terminal
终端一般就是可以用来输入一些命令，然后把该命令的执行结果输入到终端中
在计算机中，所有通过可视化界面能做到的操作都可以通过命令来完成

2、如何进入终端
> 1. 按住win+r，打开运行
  2. 输入cmd敲回车就可以进入到终端环境
  3. 控制台默认进入当前用户目录



3、命令行打开应用
> 1.  notepad   打开记事本
  2.  mspoint   打开画图
  3.  calc      打开计算机
  4.  sysdm.cpl 打开环境变量设置窗口
  5.  write     写字板
  6.

4、常用终端命令
> 1.  d:      切换盘符
  2.  cd      进入目录
  3.  dir     查看文件目录
  4.  ls      查看文件目录（window powershell）
  5.  rd      删除目录
  6.  ren     重命名
  7.  echo>   创建文件（例如echo>a.txt）
  8.  type    查看文件内容
  9.  del     删除文件
  10.  cls    清空控制台
  11.  ../ 以及 ..   回退上一级

## 05-Nodejs-运行Node.js程序的两种方式

- REPL模式
    + REPL(read-eval-print-loop)；类似于浏览器中的控制台在命令行窗口中
        * 可以使用该REPL做一些代码或者API的测试
    + <b>如何进入REPL：</b>通过终端输入`node`敲回车就可以进入
    + <b>如何退出REPL：</b>两次ctrl+c 可以退出REPL模式，或者执行.exit命令
    + 基本操作
        * 使用下划线“ _ ”，表示上一个命令的返回结果

- 命令行模式
    + 在当前目录下打开控制台
        * 在当前文件夹下，空白区域 shift + 鼠标左键，在此处打开命令窗口
        * 编辑下 下载插件
        * cmd进去到当前目录
        * 在执行文件所在的文件夹地址栏中输入cmd，弹出命令窗口

## 06-Nodejs-全局成员概述

1、全局对象

- global (`面试时可能会和window做对比`)
    + 表示Node所在的全局环境，类似于浏览器的window对象。
    + 在 Node 中没有全局作用域，都是模块作用域
    + Node全局范围中的所有成员都属于global
    + 需要注意的是，如果在浏览器中声明一个全局变量，实际上是声明了一个全局对象的属性，比如`var x = 1`等同于设置`window.x = 1`，但是Node不是这样，至少在模块中不是这样（REPL环境的行为与浏览器一致）。在模块文件中，声明var x = 1，该变量不是global对象的属性，global.x等于undefined。这是因为模块的全局变量都是该模块私有的，其他模块无法取到。

- process
    + process对象是Node的一个全局对象，提供当前Node进程的信息。它可以在脚本的任意位置使用，不必通过require命令加载。

- console
    + 指向Node内置的console模块，提供命令行环境中的标准输入、标准输出功能

2、全局函数

- setTimeout() 和 clearTimeout()
- setInterval() 和 clearInterval()
- setImmediate() 和 clearImmediate()
    + 这是一个可以用来异步执行的一个功能函数

3、伪全局对象

伪全局对象，其实是每个内部都有的方法或者对象

- exports
    + `exports` 是 `module.exrpots` 对象的一个别名
- module
    + 里面有一个属性 `exports` 专门用于模块的导出接口
- require
    + 用于加载模块
- 这四个主要用于实现模块化

4、伪全局变量

`__filename` 和 `__dirname` 常用语文件操作时候的路径拼接用的

- `__filename`
    + 获取到的是当前文件的绝对路径（包含文件名+后缀名）
- `__dirname`
    + 获取到当前文件所属的目录的绝对路径


## 07-Nodejs-模块化-初识模块化开发

> exports 与 module.exports == {}

## 08-Nodejs-模块化-模块导入导出原理分析

- module.exports和exports指向是一样的，都是一个空对象（Object的对象实例），实际导出的成员以module.exports为准
- moduel 与 module.exports
  + 一般模块导出单个成员的时候使用exports
  + 一般模块导出构造函数或者实例对象的时候使用module.exports

- 如果使用global成员公开成员，那么是不需要返回值，直接返回即可
    global.sum =sum;

- require引入对一个模块多次引用，实际上不会加载多次，因为第一次已经缓存了

## 09-Nodejs-模块化-模块相关概念补充

文件模块加载的优先级
> 系统模块-无后缀 -- .js --  .json -- .node -- 文件夹

系统模块
文件模块
文件夹
node_modules
缓存

自定义模块与系统模块优先级
> 系统模块 -- 自定义模块 <br>
>
> 即使自定义的模块与系统模块名字一样，也会只加载系统模块

## 10-Nodejs-模块化-初识包概念

什么是包
> 所谓的包就是一个模块 <br>
> 包和模块并没有本质的不同，
 包是在模块的基础上更深一步的抽象，包将某个独立的功能封装起来，用于发布、更新、依赖管理和进行版本控制

## 11-Nodejs-模块化-包相关规范分析

包规范
1. package.json必须在包的顶层目录下
2. 二进制文件应该在bin目录下
3. JavaScript代码应该在lib目录下
4. 文档应该在doc目录下
5. 单元测试应该在test目录下

package.json主要属性介绍


包结构主要事项

1. 必须有package.json文件
2. 通过main属性搜索入口文件
3. 核心模块的优先级最高
4. 同名自定义模块 不会覆盖原生模块



创建包
> npm init  <br>
> npm init -y

启动包
> npm start  <br>
> npm 文件名称

## 12-Nodejs-模块化-npm基本使用

1、npm安装
> npm 子第一个安装node的时候已经默认安装上

2、npm的含义

+ [Node.js的开放式模块登记和管理系统]
+ NodeJs默认的模块管理器
    * 是一个基于node做的一个终端中的应用程序，叫做npm

3、包的加载机制
（以加载jQuery包为例）；

1. 例如在JS文件（index.js）中写了这样一句话`require('jquery')`；
2. 首先node会在index.js所属目录下找一个叫做`node_modules`的目录
3. 如果找到`node_modules`目录，那么找该目录下有没有一个叫做`jQuery`的目录的目录
4. 如果在`node_modules`目录中找到`jQuery`的目录，
5. 那么node会在`jQuery`目录下找一个叫做`package.json`的文件
6. 如果找到`package.json`文件，那么node会在该文件中，找一个`main`的属性
7. 如果找到该属性，那么node会将该属性指定的模块路径作为加载的路径，然后加载
8. 如果在`jQuery`目录下，
    + 没有`package.json`文件，
    + 或者`package.json`文件中没有main属性
    + 或者main属性指定的入口模块不存在
    + 那么node会在`jQuery`目录下按照`index.js`、`index.json`的方式进行加载
9. 如果在上面的流程中还没有找到
    + node会自从进入当前目录的上一级目录下找'node_modules'目录开始查找，重复上面的流程
    + 直到node进入当前文件所属的根路径（例如`c:/a/b/c/foo.js`，那么根路径就是`c:/`）
    + 如果最后在根路径下还是找不到，最后报错


4、包描述文件package.json说明书

- name -- 包的名称
- description -- 包的简介
- version -- 包的版本号
- keywords -- 关键词数组，用于在npm中分类搜索
- author -- 包的作者
- main -- 配置包的入口，默认是模块根目录下的index.js
- dependencies -- 包的依赖项，npm会通过该属性自动加载依赖包
- scripts -- 指定了运行脚本命令的npm命令行缩写

5、npm常用的命令

- npm init [-y] -- 初始化一个包
- npm install [--save] 包名
    + 加上 --save参数表示将当前安装的包添加到package.json中的依赖项中
- npm uninstall [--save] 包名
    + 加上 --save，从package.json中删除依赖项
- npm install -g 报名 -- 安装一个全局 命令行工具
- npm docs 包名 -- 查看包的文档（非常有用）
- npm root -g 查看全局包安装路径
- npm config set prefix "路径" -- 修改全局包安装路径
- npm list -- 查看但钱目录下安装的所有包
- npm list -g -- 查看全局包的安装路径下所有的包
- npm update 包名 -- 更新当前目录下某个包
- npm update -g 包名 -- 更新某个全局工具包


## 13-Nodejs-模块化-模块加载方式

1. 核心模块的加载（优先级最高）
2. 文件模块的加载
3. 文件夹的加载
4. 从node_modules目录下加载
5. 从缓存加载

- 模块加载的时候require的参数要么是路径，要么是特定的字符串


朴灵 -- 《深入浅出Node.js》


## npm的问题

- 资源都在国外，有时候会被墙，导致无法下载或者很慢，解决方案
    + npm config set registry https://registry.npm.taobao.org
    + cnpm
        * 官网: http://npm.taobao.org/   
        * npm install -g cnpm --registry=https://registry.npm.taobao.org
        * 下载包时，使用 `cnpm install 包名`
    + nrm
        * 项目地址：https://www.npmjs.com/package/nrm
        * 下载 ： npm install nrm -g
        * nrm -- 查看有哪些命名
        * nrm ls -- 查看维护的镜像
        * nrm use 名称  --- 切换镜像下载包

