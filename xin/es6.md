# es6

## 块级作用域 
let const 一个大括号就是一个作用域  

## 解构赋值
```
let [a,b,c] = [10,20,30]
function fun(){
    return(1,2)
}
let[x,y] = fun()
console.log(x,y) //1,2

---

let str = "hello
let[a,b,c] = str
console.log(a,b,c) //h,e,l  

---

let user = {
    username:"zzt",
    age:20
}
let {username,age} = user
console.log(username, age) //zzt  20

function showName({username}){
    console.log(username) //zzt
}
showName(user)

---


```






