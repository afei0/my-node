# 一
npm i gh-pages 下包

{
  "name": "my-node",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
 +   "deploy": "gh-pages -d _book"
  },
 + "homepage": "https://afei0.github.io/my-node",

npm run deploy 上传到网上

gitbook build  打包

gitbook serve  启动book服务

修改文档 运行 npm run publish

# 二

npm i gh-pages

npm run build

{
  "name": "my-node",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
 +   "deploy": "gh-pages -d build"
  },
 + "homepage": "https://afei0.github.io/my-node"

 git add .

 git commit -m'1'

 git push

 npm run deploy