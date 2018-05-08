# 简化版 TODO 应用

不用 vuex ，可以实现一个非常简单的 todo 效果。也就是 https://cn.vuejs.org/v2/guide/list.html  
这里的效果。  
第一步：显示 todo 能 click 传 id

```js
<template>
  <div class="wrap" >
    <div v-bind:key="todo.id" v-for="todo in filteredTodos">
      <div @click="close(todo.id)" class="todo">
        {{ todo.text }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  methods: {
    close(id) {
      console.log('id', id)
    }
  },
  computed: {
    filteredTodos() {
      return this.todos
    }
  },
  data: () => ({
    seen: false,
    msg: 'click',
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

<style>
.todo {
  line-height: 1.9;
  border: 2px solid lightcoral;
  margin: 5px;
}
</style>
```

## 点击一个 todo ，让它隐藏

```js
<template>
  <div class="wrap" >
    <div v-bind:key="todo.id" v-for="todo in filteredTodos">
      <div @click="close(todo.id)" class="todo">
        {{ todo.text }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  methods: {
    close(id) {
      this.todos = this.todos.map(t => {
        if (t.id === id) t.compl = true
        return t
      })
    }
  },
  computed: {
    filteredTodos() {
      return this.todos.filter(t => t.compl === false)
    }
  },
  data: () => ({
    seen: false,
    msg: 'click',
    todos: [
      {
        id: '1',
        text: '第一项',
        compl: false
      },
      {
        id: '2',
        text: '第二项',
        compl: false
      }
    ]
  })
}
</script>

<style>
.todo {
  line-height: 1.9;
  border: 2px solid lightcoral;
  margin: 5px;
}
</style>
```

## 第三步：提交新 todo

keyup 是一个按键（ key 的意思是按键，keyboard 是键盘）  
每个键盘上按键都对应一个整数，Enter 键对应 13  
所以要给一个 input 添加 监听 Enter 键抬起 就用下面的语法

```js
<input @keyup.13="myFun" />
http://keycode.info/ 上可以查看每个键对应的 keycode ，按钮编码。
<template>
  <div class="wrap" >
    <input v-on:keyup.13="addTodo" v-model="userInput" />
    <div v-bind:key="todo.id" v-for="todo in filteredTodos">
      <div @click="close(todo.id)" class="todo">
        {{ todo.text }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  methods: {
    close(id) {
      this.todos = this.todos.map(t => {
        if (t.id === id) {
          t.compl = true
        }
        return t
      })
    },
    addTodo() {
      console.log('userInput', this.userInput)
      const newTodo = {
        id: (this.todos.length + 1).toString(),
        text: this.userInput,
        compl: false
      }
      this.todos.push(newTodo)
      this.userInput = ''
    }
  },
  computed: {
    filteredTodos() {
      return this.todos.filter(t => t.compl === false)
    }
  },
  data: () => ({
    userInput: '',
    todos: [
      {
        id: '1',
        text: '第一项',
        compl: false
      },
      {
        id: '2',
        text: '第二项',
        compl: false
      }
    ]
  })
}
</script>

<style>
.todo {
  line-height: 1.9;
  border: 2px solid lightcoral;
  margin: 5px;
}
</style>
```
