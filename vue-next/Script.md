# NPM 脚本

npm 脚本，也就是 npm script 。是写到 package.json 的 script 一项下面的小脚本。一个脚本就是一串小命令。创# 建 npm 脚本

```
mkdir my-project
cd my-project
npm init -y
```

创建项目，里面添加 package.json 。一个 npm 脚本看上去是这样的。

```
"scripts": {
"脚本名": "具体命令"
},
```

首先，一个 npm 脚本，必须被写到 script 一项之内。由脚本名和具体命令组成。

```
npm run 脚本名
```

这样实际得到执行的是”具体命令“。

## 注意点

执行 npm run 脚本名 的系统位置，必须是跟 package.json 平级。也就

```
ls
```

可以看到 package.json 的位置。

如果不在这个位置执行。

```
enoent ENOENT: no such file or directory, open '/Users/peter/package.json'
```

没有找到 package.json

解决方法：cd 进入 package.json 所在文件夹，再来执行 npm run 系统命令 。

## vue-cli 自动生成的三个脚本

```
  "scripts": {
    "serve": "vue-cli-service serve --open",
    "build": "vue-cli-service build",
    "lint": "vue-cli-service lint"
  },
```

`serve` 是启动本地开发服务器  
`build` 是进行产品化编译  
`lint` 是运行 eslint
