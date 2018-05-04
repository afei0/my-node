# 源码架构

来搭建基本代码架构

## 脚手架默认源码

```
$ cd src
$ ls
assets components main.js App.vue
```

assets 本意是”资产“，这里的意思是静态资源，图片/CSS 等等一切不需要运算就可以直接被浏览器使用的都可以叫静态资源。那 js 算不算静态资源呢？如果是直接可以被浏览器运行的 js ，也可以认为是静态资源。所以静态资源并不是本身不执行，而是交给浏览器之前，不需要做预先的运算处理  
components 里面放项目组件  
main.js 是项目入口文件  
App.vue 是项目入口组件

## 确定 CSS 架构

来定一下全局 css 写到哪里，组件局部 css 怎么写。

##### App.vue

```
<style>
body {
  margin: 0;
}

* {
  box-sizing: border-box;
}
</style>
```

全局的 css 写到整个项目的入口组件，或者说就是老祖宗组件中的 script 标签之内。  
整个 App.vue 改成下面的样子

##### App.vue

```
<template>
  <div>
    <Layout />
  </div>
</template>

<script>
import Layout from './components/Layout.vue'

export default {
  name: 'app',
  components: {
    Layout
  }
}
</script>

<style>
body {
  margin: 0;
}

* {
  box-sizing: border-box;
}
</style>
```

##### Layout.vue

```
<template>
  <div class="layout">
    Hello
  </div>
</template>

<script>
export default {
  name: 'Layout'
}
</script>

<style scoped>
.layout {
  color: red;
}
</style>
```

删除 HelloWorld.vue ，创建 Layout.vue 。局部 css 就写到各个组件内部的 style 标签下。 `scoped` 的意思是 ”限制作用域“，加上它，就保证了当前组件的 css 中，即使 class 名跟他组件中重复，也不会造成样式的互相影响。

## vue 组件的三大要素

一个 vue 组件就是一个 .vue 的文件。里面包含三种类型的代码。  
template 模板，有些智能的 html  
script 脚本，这里面写 JS 代码 ，JS 也是一种脚本语言  
style 样式，里面写 css

## Vue 组件如果供父组件使用

一个被调用的组件，叫 子组件 ，调用它的组件叫 父组件 。要想调用成功，有以下几个步骤：  
子组件中要在 export default 语句内，添加 name: '组件名'  
父组件中首先要进行导入 import 组件名 from ‘./组件'  
父组件中还需要声明自己的子组件，例如 components: { 组件, 组件}  
父组件中使用要用类似 html 标签的形式 <组件名 />
