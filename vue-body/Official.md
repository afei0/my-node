# vue 官网教程

把官方的 vue 教程，按照我们自己的 webpack 的思路来做一遍。

## 区分教程和 API 文档

https://cn.vuejs.org/v2/guide/ 官网是学习一个东西的重要的资源。官网上最重要的有两个东西  
教程，有时候叫指南，有时候叫起步，其实都是一个东西。教程的内容不求全，只求动手和实用。  
API docs ，也就是 API 文档。API 文档比较全面。  
新手应该看的是教程。

## 什么是 Vue ？

Vue 是一个做 UI ，或者说做界面的框架。学习 Vue 需要对 html/css/js 有基本的掌握。

## Hello World

现在，我们实用 vue-cli 来创建一个 Hello World 。

```js
npm i @vue/cli
```

安装命令 。

```js
vue create demo
```

创建一个项目名为 demo 。  
进行项目要运行那个命令启动呢？运行 npm start 会发现没有 start 这个 npm 脚本 。  
于是打开 package.json 可以看到有如下的 npm 脚本：

```js
"serve": "vue-cli-service serve --open",
"build": "vue-cli-service build",
"lint": "vue-cli-service lint"
```

可以看到有三个 npm 脚本。其中，serve 是启动服务器的意思。

```js
npm run serve
```

启动应用。浏览器中，打开的页面中可以看到应用运行的效果。里面自带一个 HelloWorld 组件。  
##适当跳过一些概念  
继续官网教程，会看到 “声明式渲染”，初学者不必去理解，经管这个概念对 vue 本身具有革命性意义。它革的是 jquery 的 “命令式 DOM 操作” 的命。

## 添加组件内数据

Vue 把组件内数据叫做 data ，其实也可以叫做 state 也就是 状态 。

##### App.vue

```js
<template>
  <div id="app">
    <HelloWorld />
  </div>
</template>
App.vue 模板中，只保留 HelloWorld 组件。
```

##### HelloWorld.vue

```js
<template>
  <div class="hello">
    {{ msg }}
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    msg: 'Helle Everyone'
  })
}
</script>
```

HelloWorld 组件中，来使用一个 data 。两个注意点：  
模板中使用的时候，变量名用双花括号包裹  
脚本中定义的时候，要用函数的返回值的形式。

除了可以把 data 设置为页面文本之外。当然也可以用它来做 html 标签的属性值。

##### HelloWorld.vue

```js
<template>
  <div class="hello" title="msg">
    {{ msg }}
  </div>
</template>
```

但是如果直接把 data 的变量名，这里就是 msg 传递给 title ，到浏览器中鼠标滑过，看一下，会发现 msg 并没有按照变量去解析，而是直接显示成了字符串。

##### HelloWorld.vue

```js
<template>
  <div class="hello" v-bind:title="msg">
    {{ msg }}
  </div>
</template>
```

如果想要让 msg 转换成自己的值，也就是 Hello Eveyone 。就需要用到 v-bind 。  
后续我们会在模板中看到很多以 v- 打头的关键字，这些都叫做 Vue 指令 。v-bind 中 bind 的意思就是绑定。用来他之后，就可以把一个 html 属性（ attribute ）跟一个变量做绑定。

现在页面中，鼠标再次滑过，可以看到浏览器中显示的信息就是 Hello Everyone 了。可见此时 v-bind 后面的这个 msg 已经被当做变量处理了。

条件指令那么指令的实质是什么？在 JS 语言中，原生的各种机制可以用来控制代码逻辑，例如，变量使用，条件，循环等等。但是，在 html 中，是没有这些机制的。那么指令应运而生。就是为 html 添加逻辑上的功能。例如，v-bind 这个指令，用来绑定变量。如果要实现循环，就要用另外一个指令 v-if 。

<div v-if="false">
  你能看到我吗？
</div>
上面代码中，如果 v-if 的值是 false ，那么字符串就不会显示在页面上，如果是 true 就会显示。
<template>
  <div class="hello" v-bind:title="msg" >
    {{ msg }}
    <div v-if="seen">
      你能看到我吗？
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    seen: false,
    msg: 'Helle Everyone'
  })
}
</script>

但是 v-if 通常都是配合变量使用的。添加新数据 seen 。可以用 seen 来控制 v-if 。如果 seen 改为 true ，v-if 所在的 div 就会出现在页面上，seen 为 false 的时候 div 就会被隐藏掉。

## 循环指令

```js
todos: [
  { text: '学习 JavaScript' },
  { text: '学习 Vue' },
  { text: '整个牛项目' }
]
```

data 中添加这些数据。

```js
  <li v-for="todo in todos">
      {{ todo.text }}
    </li>
```

模板中，就可以用 v-for 指令来逐一显示了。

```js
<template>
  <div class="hello" v-bind:title="msg" >
    ...
    <div v-bind:key="todo.id" v-for="todo in todos">
      {{ todo.text }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    todos: [
      {
        id: '1',
        text: '第一项'
      },
      {
        id: '2',
        text: '第二项'
      }
    ]
  })
}
</script>
```

但是，每一个迭代项目要求都有有独一无二的 key 值。所以代码中添加 id 。

```js
  <Button v-on:click="showMsg">{{ msg }}</Button>

  methods: {
    showMsg() {
      this.seen = true
    }
  },
```

这里我们的按钮上如果发生了 click 事件，就可以通过 v-on 指令来给它指定事件处理函数。这里 showMsg 就是一个事件处理函数，其实也就是一个普通函数。  
到 script 标签下，定义一个函数，需要定义 methods 对象。这里可以看到事件处理函数 showMsg 的定义了。其中如果要操作 data ，那变量名前面要添加 this 。  
seen 变量一旦被改成 true 那么对应的 v-if div 就会被看到了。Vue 组件式所谓叫做“响应式的”，意思是，只要数据变化了，那么组件会自动重新加载新数据，或者可以认为组件会自动局部刷新。
