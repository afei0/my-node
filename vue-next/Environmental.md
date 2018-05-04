# Vue 开发环境搭建

如果看 Vue 的官网，会发现 Vue 安装形式不唯一，最简单的方式其实是用 script 标签引入。这个对新手是最友好的。但是我们本课程中不采用这用方式，原因有二：第一，标签引入的方式不够专业，专业开发者基本上都是用 webpack 开发的；第二，标签方式，使用语法跟 webpack 方式还是有些差异的，学多了也是浪费时间。

# 用 Vue-cli 来进行环境搭建

vue-cli 是 Vue 官方提供的命令行工具，用来搭建 vue 的开发环境。

```js
npm i -g @vue/cli
```

这样可以安装最新的 vue-cli 版本。  
-g 参数，意思是 globally 全局安装，全局安装目的都是为了获得一个可以在命令行直接执行的系统命令  
@ 是 npm ，也就是包管理工具提供的最新功能，不属于 vue 的功能。@ 的意思是命名空间 （ namespace ) 。简单来说就是一个文件夹。@vue 就是从 vue 的文件夹中，去安装 cli 。这个安装好之后就是最新版的 vue-cli 了。

系统上新装一个命令之后，一般要重新打开一个命令行窗口才能执行，当前命令行窗口有可能找不到该命令。具体要执行哪个命令，要从 官网 查看。

```js
$ vue --version
3.0.0-beta.9
```

查看 vue 的版本，可以看到安装是 3.0 以上版本，是目前的最新版。beta 意思是“公测版本” 。

```js
vue create mobile-layout
```

创建项目脚手架代码，项目名叫 mobile-layout 。

## 第一个问题

```js
Please pick a preset
```

### 请选择一个配置

系统给出了两个选项

```js
default (babel, eslint)
 Manually select features
```

第一个 default 意思是默认值。默认中包含两项：
babel 是用来编译 ES6
eslint 是做语法检查的第二 Manually 是手动选择，这个适合高手用。所以直接回车，选择默认值。

```js
Your connection to the the default npm registry seems to be slow.
Use https://registry.npm.taobao.org for faster installation? (Y/n)
```

### 你到默认的 npm 网站的网络不给力，是不是考虑使用国内的淘宝镜像？

这里我们直接回车，使用淘宝镜像。

```js
🎉  Successfully created project mobile-layout.
👉  Get started with the following commands:

 $ cd mobile-layout
 $ npm run serve
```

成功的创建了 mobile-layout 这个项目请用下面的两个命令开始开发回车进行安装，装好之后会看到这样的信息。serve 是启动服务器的意思。server 是服务器， serve 就是服务器的动词形式。

```js
npm run serve
```

就会启动开发服务器，项目就会被运行在 8080 端口上了。  
这里，搭建开发环境就完成了。

# 脚手架基础代码简介

到项目顶级位置，用 ls 查看会看到

```js
node_modules package.json src
package-lock.json public
```

各自的作用是：  
node_modules 是 npm 进行局部安装的时候的安装位置，也就是说，只要安装的时候不加 -g 参数，那么被安装的 npm 包，就会被保存到这个文件夹。  
package.json 中有几个功能，最主要的有两项：第一项，记录所有局部安装的包。第二项，添加 npm 脚本  
src 里面是项目真正的源码  
package-lock.json 里面详细记录的被安装的 npm 包，已经被安装的依赖包的精确版本。在项目被他人从 github 上下载后，再次安装提供便利。直接一个 npm i 就可以安装好项目的所有包了。  
public 是公开的意思。放在这里面的东西，可以被浏览器直接访问到。一般放静态资源。

# 修改 npm 安装源

```j
npm config set registry https://registry.npmjs.org/
```

```js
vue create ccccc --registry='https://registry.npmjs.org'
```

在 vue create 之后选择淘宝安装源，可能会安装失败。这时候解决方法就是改回官方的安装源。可以通过上面的命令来实现。ccccc 替换成自己的项目名。
