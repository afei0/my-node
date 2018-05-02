## ajax (同步 异步)

原生的 ajax 请求 ---> jq 的请求 --->promise 类(fetch exios) 请求

发送原声的 ajax 请求 1.创建 XMLHttpRequest 对象 2.使用该对象的 open 方法，规定请求的方法和地址还有是否异步请求的方法 GET(通常用来获取数据) POST(通常用来传递数据)
open 第二个参数代表 请求的地址
open 第三个参数代表 请求是否异步 true 异步 3.使用该对象的 send 方法发出请求
api

## GET 请求

```js
let xhr = new XMLHttpRequest()
xhr.open('GET', 'https://api.github.com/users/afei0', true)
xhr.send()
xhr.onreadystatechange = function() {
  // onreadystatechange 请求发出时的监听事件
  // readyState 请求的状态
  // status 状态码
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log(xhr.responseText)
    // responseText 后台相应之后返回的数据
    // 现在的 ajax 请求返回的都是 json 字符串
    // json 是一种数据类型 前后台传递 比较有优势
    // 体积小 传输快 易于处理
    // 将json数据转化为对象 JSON.parse(json数据)
    // 使用 JSON.stringify()
    console.log(JSON.parse(xhr.responseText))
    console.log(JSON.parse(xhr.responseText).login)
  }
}
```

## POST 请求

```js
let xhr = new XMLHttpRequest()
xhr.open('POST', 'https://cnodejs.org/api/v1/accesstoken', true)
//因为POST请求需要向后台传递数据 默认是 xml 类型 现在都是 json 类型 所以需要设置请求头 为 json 类型
xhr.setRequestHeader('Content-type', 'application/json')
//send (向后台发送的数据 类型必须是 json 类型)
xhr.send('{"accesstoken":"32167b8d-2f98-4df7-9148-b14169f31563"}')
xhr.onreadystatechange = function() {
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log(xhr.responseText)
  }
}
```

## jquery 的 ajax 请求

```js
import $ from "jquery"
$.ajax({
    type: "GET",
    // type请求的数据类型
    url: "https://api.github.com/users/afei0",
    // url 请求的地址
    success: function (msg) {
    // success请求成功后 执行的函数里面的参数代表返回的数据
        console.log(msg)  
    },
    error:function(err){
        console.log(err)
    }
})

---

import $ from "jquery"
$.ajax({
    type: "POST",
    url: "https://cnodejs.org/api/v1/accesstoken",
    data: { "accesstoken": "32167b8d-2f98-4df7-9148-b14169f31563" },
    // data 向后台传递的数据 没有必要设置成json格式 直接传递对象即可 因为jq内部帮我们自动转化
    success: function (msg) {
        console.log(msg)
        root.innerHTML = `<img src=${msg.avatar_url}>`
    }
})
```

## axios

npm i axios --save 安装 axios

#### axios GET 方法

```js
import axios from 'axios'
// axios get方法
// then 成功后 执行的函数 该函数里面的参数 是一个axios 自定义对象 该对象下有一个data属性 这个属性就是后台相应的数据
let username = 'whrgithub'
axios
  .get(`https://api.github.com/users/${username}`)
  .then(function(res) {
    // 成功后执行
    console.log(res.data)
  })
  .catch(function(error) {
    //失败后执行
    console.log(error)
  })
```

#### axios POST 方法

```js
import axios from 'axios'
axios
  .post('https://cnodejs.org/api/v1/accesstoken', {
    accesstoken: '32167b8d-2f98-4df7-9148-b14169f31563'
  })
  .then(function(response) {
    console.log(response)
    // 成功后执行
  })
  .catch(function(error) {
    console.log(error)
    // 失败后执行
  })
```

## Performing multiple concurrent requests

```js
function getUserAccount() {
    return axios.get('https://api.github.com/users/whrgithub');
}
function getUserPermissions() {
    return axios.get('https://api.github.com/users/afei0');
}
axios.all([getUserAccount(), getUserPermissions()])
    .then(function (acct) {
        console.log(acct[0].data);
        console.log(acct[1].data);
        // 两个请求全部结束之后 要做的事
        // Both requests are now complete
    });

---
function getUserAccount() {
    return axios.get('https://api.github.com/users/whrgithub');
}
function getUserPermissions() {
    return axios.get('https://api.github.com/users/afei0');
}
axios.all([getUserAccount(), getUserPermissions()])
    .then(axios.spread(function (acct, perms) {
        console.log(acct.data);
        console.log(perms.data);
        // Both requests are now complete
    }));
```
