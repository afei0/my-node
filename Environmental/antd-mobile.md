本文将介绍使用Create-React-App脚手架搭建antd-mobile的开发环境。

### 快速开始：
```js
npm install -g create-react-app       /* 安装create-react-app，建议使用cnpm */

create-react-app myapp                 /* 使用命令创建应用，myapp为项目名称 */

cd myapp                                        /* 进入目录，然后启动 */

npm start
```
按以上执行，即可快速创建React开发环境。

打开http://localhost:3000/ 查看

### 环境配置介绍：

### 一、项目结构：

生成项目后，脚手架为了“优雅”... ...隐藏了所有的webpack相关的配置文件，此时查看myapp文件夹目录，会发现找不到任何webpack配置文件。执行以下命令：
```js
npm run eject
```
再查看myapp 文件夹，可以看到完整的项目结构：
```js
myapp/

    node_modules/

    package.json

    .gitignore

    config/

        paths.js

        polyfills

        env.js

        webpack.config.dev.js

        webpack.config.prod.js

    public/

        index.html   / 入口html文件 /

    scripts/

        build.js

        start.js

        test.js

    src/

        App.js

        index.js    / 主入口文件 /
```
以上加粗文件为主要配置文件。

### 二、项目配置介绍

此处需要有npm、webpack的基础知识，充电传送门：[webpack学习教程](http://www.jianshu.com/p/42e11515c10f)

查看package.json文件的scripts，
```js
"scripts": {

    "start": "node scripts/start.js",

    "build": "node scripts/build.js",

    "test": "node scripts/test.js --env=jsdom"

},
```
可知，运行时是直接执行scripts文件目录下的js文件。

其中*start.js*为开发环境，*build.js*为打包脚本。

开发环境，代理请求

查看start.js, Facebook基本为每项配置都写了详尽的注释，

start.js脚本启动了dev-server, 这里需要了解的是
```js

function addMiddleware(devServer){

    ... ...

    这个函数调用http-proxy-middleware模块，将代理请求，代理地址在package.json中添加

}
```
在package.json中添加字段proxy，开发环境下dev-server将会自动转发请求：

```js
"proxy": "http://aaa.bbb.com"
```
SASS、LESS等CSS预处理器配置

Facebook官方在create-react-app升级到某一版本，突然丢掉了默认对sass、less等预处理器的支持，官方文档说明

于是，只能自己动手，在config目录下，webpack.config.dev.js 和 webpack.config.prod.js文件，没有抽出 loader、postcss之类一般共用的配置，于是，在两个文件夹都要一起配置，也可以抽出共用部分，以便维护。

这里以webpack.config.dev.js举例，webpack.config.prod.js一样配置即可：

SASS-loader：

1、命令行，在当前目录执行：
```js
npm install sass-loader node-sass --save-dev
```

链接：https://www.jianshu.com/p/5e6c620ff4d6
來源：简书