# 布局文件

通常一个项目中有多个页面，每个页面其实有一部分内容是公用的，例如 header/footer/sidebar 这些。有的项目中，把公用部分都放到一个文件中，这个文件就是 布局文件 。

## 添加布局文件

布局的英文是 Layout ，所以我们可以把 header 和 footer 的内容都放到 Layout.vue 。

##### components/Layout.vue

```js
<template>
  <div class="layout">
    <Header />
    不同页面显示区域
    <Footer />
  </div>
</template>

<script>
import Header from './Header'
import Footer from './Footer'
export default {
  name: 'Layout',
  components: {
    Header,
    Footer
  }
}
</script>

<style scoped>
.layout {
  color: red;
}
</style>
```

布局文件的构成，通常有 Header/Footer ，还有可变部分组成。

```js
<template>
  <div>
    Header
  </div>

</template>

<script>
export default {
  name: 'Header'
}
</script>
```

Header 写成这样。

```js
<template>
  <div>
    Footer
  </div>
</template>

<script>
export default {
  name: 'Footer'
}
</script>
```

Footer 写成这样  
这里的“可变部分”，我们会通过 vue-router 来实现。

## 关于 CSS

这个跟 vue 无关，但是也非常实用的一个 css 的原则。  
CSS 要根据组件层级，进行合理的层级划分，基本上就是一个组件的位置和大小，最好能在父组件中指定  
例如，我们这里的 Header 和 Footer ，他们的位置，最好是在 Layout 中用 CSS 控制，一些细节再去各自组件中写。

##### components/Main.vue

```js
<template>
  <div class="main">Main</div>
</template>

<script>
export default {
  name: 'Main'
}
</script>

<style scoped>
.main {
  background-color: green;
  height: 130vh;
  overflow: scroll;
}
</style>
```

假设 Main 组件中，内容很多，超出了整个屏幕的高度。

##### components/Layout.vue

```js
<template>
  <div class="layout">
    <div class="header-wrap">
      <Header />
    </div>
    <div class="main-wrap">
      <Main />
    </div>
    <div class="footer-wrap">
      <Footer />
    </div>
  </div>
</template>

<script>
import Header from './Header'
import Footer from './Footer'
import Main from './Main'
export default {
  name: 'Layout',
  components: {
    Header,
    Footer,
    Main
  }
}
</script>

<style scoped>
.layout {
  color: red;
  display: flex;
  height: 100vh;
  flex-direction: column;
}

.footer-wrap,
.header-wrap {
  border: 1px solid lightblue;
  min-height: 40px;
}

.main-wrap {
  flex-grow: 1;
  background-color: lawngreen;
  overflow: scroll;
}
</style>
```

Layout.vue 中做合适的处理，就能一直保证 header 和 footer 位置不变。
