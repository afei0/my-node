## 笔记

```js
v-bind:  简写   :
v-on:   简写    @


<style scoped> 限制作用域  
.reverse() 数组逆序
v-bind:key="comment.id"
v-for="comment in comments"
v-model 不仅仅能在 input上用，在组件上也能使用，下面是一个和 Vue 官网教程类似的例子

### export default
computed  计算属性  

computed:() => 'xxx'
<input v-model="message" placeholder="请填写评论" />

  //  v-model="message" 获取表单内容

<button @click="handleClick">提交</button>

---

export default {
  name: 'CommentBox',
    computed: {
    //计算属性
      reversedComments() { return this.comments.slice().reverse() }
      // reversedComments:function(){
      //   return this.comments.slice().reverse()
      // }
  },
  data:()=>({
    comments: [
      {
        id:1,
        body:'评论1'
      },
      {
        id:2,
        body:'评论2'
      }
    ]
  }),
  methods:{
    // 方法  函数
    handleClick(){
      console.log(1);

    }
  }
}
---
computed: {
      // reversedComments() { return this.comments.reverse() }
      reversedComments:function(){
        return this.comments.slice().reverse()
        //逆序问题  reverse() 逆序操作修改数组本身
        //.slice()  数组拷贝   不变性原则
        // ... 展开运算符
      }
  },
```

##### router.js

```js
import Vue from 'vue';
import Router from "vue-router";
import Post from "@/components/Post";
import Home from "@/components/home";

Vue.use(Router)
export default new Router({
    routes:[
        {
            path:'/',
            component:Home
        },
        {
            path: '/post',
            component: Post
        }
    ],
    mode: 'history',

    path: '/post/:id',  :id   动态路由
    //mode 模式   切换到history模式   去掉 #
})

--

methods:{
    handleClick(){
        this.$store.commit('addComment',comment)
        // .commit 执行
        this.message = ''

    }
  }
```
