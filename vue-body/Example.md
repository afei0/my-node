# Vue 官网教程：起步

https://cn.vuejs.org/v2/guide/instance.html

## 选项 option

##### main.js

```js
new Vue({
  render: h => h(App)
}).$mount('#app')
```

脚手架戴梦得入口文件 main.js 中，默认就 new 了一个 Vue 的实例。在 Vue() 括号里面，就能传人选项了。选项就是对 vue 的一些基础配置。目前就只是，指定了一个渲染 （ render ）属性，里面规定，要渲染到页面上的组件就是 App 。后续会添加其他选项进来。

##### 生命周期钩子

每个 Vue 组件在被创建时都要经过一系列的初始化过程，这个过程中，随着时间的推移会有很多函数被自动触发执行。钩子（ hook ）其实就是一个函数，只不过他是挂到了一个特定时间点上自动被执行的函数。官方上钩子给出了多个，新手需要掌握的就是一个 created 。  
created 会在组件被创建后的那个瞬间被 自动 触发。里面我们通常会写一些加载数据的操作。

## 计算属性

先看例子

```js
msg: 'hello'
```

如果有数据 hello 我希望页面上显示的是逆序的 Hello ，那么就涉及到对原始数据要做一下计算。这个时候就要用到计算属性。

```js
  computed: {
    reversedMsg() {
      return this.msg
        .split('')
        .reverse()
        .join('')
    }
  },
```

跟 data 和 methods 平级，添加 computed （计算后的）这一项。里面如果定义一个函数叫做 reversedMsg 这个函数的返回值，就可以在模板中，通过 reversedMsg 这个变量名获取到。
再来讨论一下， computed 的意义是什么呢？其实子模板中，我们也可以进行简单的计算，但是这是不推荐的。这样会把模板弄的很乱，模板的作用还是侧重显示 html 的。所以就会把计算过程移动到 computed 一项下面来完成。而模板中就可以直接以一个变量名，拿到最后的结果了。
