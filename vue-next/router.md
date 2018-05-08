# Vue Router

先在我们要让 Layout 组件的核心区域，随时切换内容。可以通过 vue-router 来完成。

## 配置 vue-router

```js
npm i vue-router
```

装包。

##### src/router.js

```js
import Vue from 'vue'
import Router from 'vue-router'
import Home from '@/components/Home'
import Me from '@/components/Me'
import Book from '@/components/Book'

Vue.use(Router)

export default new Router({
  routes: [
    {
      path: '/',
      component: Home
    },
    {
      path: '/book',
      component: Book
    },
    {
      path: '/me',
      component: Me
    }  ]
})
<template>
  <h1>Home</h1>
</template>

<script>
export default {
  name: 'Home'
}
</script>
```

要创建的三个页面组件，都写成最简单的形式，各个组件改一下自己的组件名。分别是 Home ，Book , Me 。

##### main.js

```js
import Vue from 'vue'
import router from './router'
import App from './App.vue'

Vue.config.productionTip = false

new Vue({
  router,
  render: h => h(App)
}).$mount('#app')
```

main.js 中导入 router 配置。

##### Layout.vue

```js
<div class="main-wrap">
  <router-view />
</div>
```

删除 src/components/Main.js ，到 Layout.vue 中，把对应显示 Main 组件的部分替换为 router-view 。  
vue-router 默认采用哈希路由，所以链接中会默认有哈希符。

##### router.js

```js
mode: 'history',
```

router.js 的路由配置对象中，添加 mode history ，就会调用浏览器底层的 history 接口，来让单页面应用看上去有多个页面的效果 。浏览器中，分别访问 / ，/book 都可以成功切换页面了。

## 使用链接

##### Footer.vue

```js
<template>
  <div>
    <router-link to="/">首页</router-link>
    <router-link to="/book">书架</router-link>
    <router-link to="/me">我的</router-link>
  </div>
</template>
```

通过 router-link 可以使用前面定义的路由。  
浏览器中，点各个链接，发现都能正确切换了。
