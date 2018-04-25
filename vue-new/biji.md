<style scoped> 限制作用域  
.reverse() 数组逆序   
v-bind:key="comment.id"   
v-for="comment in comments"   


### export default
computed  计算属性  
```js
computed:() => 'xxx'

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
