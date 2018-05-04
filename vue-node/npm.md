# 使用 npm 包

JS 是一个很有爱的社区。一些常用的功能代码，都由数以百万计的开发者，打包成数量以十万计的 npm 包，放到了 npmjs.org 这个网站上，供大家免费使用。

## 安装 npm 包

系统上安装了 nodejs 之后，就自动安装了 npm 这个命令，可以通过这个命令来安装 npm 包。但是一般装包之前，先要创建一个 package.json 文件。

```js
mkdir demo
cd demo
npm init -y
```

创建 demo 这个项目，然后在里面，运行 npm init -y 就可以生成一个 package.json 文件了。package.json 中会记录我们对这个项目安装的所有的包，以及它们的版本，便于后续在一个新环境下，再次一键完成所有包的安装。

```js
npm i axios
```

下面来安装 axios 这个包。注意，这里没有使用 -D 参数，意思是这个包，是普通安装，凡是在产品上线后，运行的时候也需要的包，都以这种方式来安装。而只是在开发过程中使用的包，例如 webpack ，就会用 -D 参数，意思是仅在开发环境下安装。

### 使用 npm 包

npm 包，都可以以 ES6 模块的形式，导入后使用。之前我们已经搭建好了 webpack 打包环境，所以可以来使用 ES6 模块和 npm 包了。

##### index.js

```js
import axios from 'axios'

axios.get('https://api.github.com/users/happypeter').then(res => {
  console.log('My username:', res.data)
})
```

index.js 中使用 axios ，请求 github API 。

```js
npm run build
```

浏览器中，打开 index.html ，是可以看到从 github 请求得到的信息的。
[](../img/1525231989519-77683288-b486-41d8-ab52-f226d9143247.png)
