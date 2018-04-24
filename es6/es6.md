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

```

## 箭头函数

(参数)=>返回值  
(参数)=>{ 操作 如果想要返回值的话 return }  
当参数不是一个的时候(0个或多个) 使用小括号  如果只有一个参数的时候可以省略小括号  
箭头函数内部的 this 指向在声明的时候就规定好了  
通常对象的属性值不能写箭头函数
当箭头函数没有操作直接返回对象的话使用 ({})  let sum = () => ({name:"zzt"})  

## 字符串模板

函数的默认参数Default 和剩余参数Rest 

```js

function sum(a,b){
    let x = a ||10
    let y = b ||10
    console.log(x*y)
}

function sum(a=10,b=10){
    给a,b传个默认值
    console.log(a*b)
}

---

let user = {
    name:"zzt",
    age:20
}
// console.log("my name is"+user.name+"my age is"+user.age)  
console.log(`my name is ${user.name},my age is ${user.age}`)  //字符串拼接

---

普通函数的arguments
箭头函数没有arguments 使用剩余参数代替 Rest 
剩余参数只能当做最后一个参数

function sum(){
    console.log(arguments)
    //输出一个类数组
}
sum(1,2,3,4,5,6)

---

let sum = (...rest)=>console.log(rest) 

输出一个数组
sum(1,2,3,4,5,6)

let sum = (a,...rest)=>console.log(rest) 
输出[2,3,4,5,6]
sum(1,2,3,4,5,6)
---

```

## 扩展操作符 spread

扩展操作符是另一种形式的语法糖  

```js
let arr = [1,2,3]
let arr1 = [4,5,6]
1
    // let newarr = arr.concat(arr1)
    // 数组拼接
2
let newarr = [...arr,...arr1,7,8,9,10]
... 把arr展开

console.log(newarr)

---

let user = {
    name:"zzt",
    ags:20
}
let user1 = {
    hobby:"computer"
}
1
    // let newuser = {}
    // for(const key in user){
    //     newuser[key] = user[key]
    //     拼接
    // }
2
    // let newuser = {...user,...user1}
3*
    let newuser =Object.assign(user,user1)

```
## 数组的新方法

### reduce 累加
把数组每一项相加 

```js

var sum = [0,1,2,3].reduce((a,b) => a+b,0)
a代表最终的结果
b代表数组的每一项
第二个参数 0 代表最终结果的初始值
console.log(sum) //6

---

let shopping = [
    {
        goodsname: "榴莲",
        price: 200,
        num: 2
    },
    {
        goodsname: "牛油果",
        price: 40,
        num: 5
    },
    {
        goodsname: "杨桃",
        price: 100,
        num: 2
    }
]
var sub = shopping.reduce((a, b) => b.price * b.num + a,0)
console.log(sub) //总价800

---

let goodsarr = [
    {
        goodsname:"榴莲",
        id:12
    },
    {
        goodsname: "牛油果",
        id: 13
    }
]
let goodid = goodsarr.reduce((obj,item) =>{
    obj[item.id] = item
    return obj
},{})
console.log(goodid);

//得到一个商品一个新对象 ：id 对象
//12：{goodsname:"榴莲",id:12}
//13：{goodsname:"牛油果",id:13}

```

### copyWithin 

copyWithin 
```js
```

### includes 

数组.includes(元素)   判断元素在数组中是否存在 存在返回true 不存在返回false 



## map 映射

map 遍历数组每一项

```js
arr = [1,2,3,4,5,6]
let newarr = arr.map(item => item*item)
console.log(newarr) //1,4,9,16,25,36

```

## filter 筛选 过滤

filter

```js
let userarr = [
    {
        name:"zzt",
        age:20
    },
    {
        name:"xiaowang",
        age:22
    },{
        name:"xiaohong",
        age:23
    },{
        name:"xiaohei",
        age:25
    }
]
let newarr = userarr.filter(item =>item.age < 23)

```

## indexOf 
indexOf 查找元素在数组中第一次出现的位置
```js
let arr = [1,2,3,4,5,6]
console.log(arr.indexOf(1))

---


```

## find 

find 
    find有三个 参数 item 每一项 index 索引值 arr 原数组
```js
let userarr = [
    {
        name:"zzt",
        age:20
    },
    {
        name:"xiaowang",
        age:20
    },{
        name:"xiaohong",
        age:20
    },{
        name:"xiaohei",
        age:20
    }
]
console.log(userarr.find((iten,index,arr) =>item.name ==='xiaohong'))

```
## findIndex

findIndex












