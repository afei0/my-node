## 笔记
```js
<style scoped> 限制作用域  
.reverse() 数组逆序   
v-bind:key="comment.id"   
v-for="comment in comments"   
v-model 不仅仅能在 input上用，在组件上也能使用，下面是一个和 Vue 官网教程类似的例子

### export default
computed  计算属性  

computed:() => 'xxx'
<input v-model="message" placeholder="请填写评论" />
<button @click="handleClick">提交</button>

export default {
  name: 'CommentBox',
    computed: {
    //计算属性
      reversedComments() { return this.comments.reverse() }
      reversedComments:function(){
        return this.comments.reverse()
      }
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
```
