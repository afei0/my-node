## 完成版 TODO ( UI 部分)

划分组件  
https://github.com/haoqicat/vtodo/commit/754d16f897480ae87a94f52ca21c232728dd4fa1  
十分钟设计课  
第一要选定的色盘上本身几种颜色都搭配。可以到 http://colorhunt.co/ 选一套高手做好的色盘。  
色盘上，选一种颜色作为**主色** ，然后选一种跟它形成最明显反差的颜色作为 **强调色** 。主色做背景用，强调色用来做按钮。

选定色盘后，代码中建议建立色盘文件

##### src/constants/palette.js

```js
export const PRIMARY_PINK = '#F8D5F0' // PRIMARY 主要
export const ACCENT_BLUE = '#41A4C3' // ACCENT 强调
export const ACCENT_LIGHT = '#58D5D3' // 浅
export const ACCENT_DARK = '#3F4B83' // 深强调色
```

## Vue 中使用色盘文件

vue 的 style 标签下默认是不能使用变量的。需要安装 sass 的支持。

```js
npm i vue-sass node-sass
```

然后，按照 https://github.com/haoqicat/vtodo/commit/16548317a2cffd1fa5107f4f9e8531f97dbd025d 方式来添加色盘即可。
