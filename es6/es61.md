# es6

## class 类 
class 
```js
// 之前的写法
function fun (name){
    this.name = name
}
//prototype 原型
person.prototype.sayName = function(){
    console.log(`my name is ${this.name}`)
}
let hyf = new Preson('黄毅飞') 
hyf.sayName() //my name is 黄毅飞
consolelog(hyf) //name :黄毅飞

----

// class
class fun{
    // constructor 是默认的方法 不设置也会存在，这个方法，在实例化对象的时候会立即执行
    constructor(name){
        this.name = name
    }
    //class 内部只能定义方法 方法之间不能使用逗号 ,
    sayName(){
        console.log(`my name is ${this.name}`)
    }
}
let hyf = new Preson('黄毅飞') 
//new 加类名字加括号  new Preson('黄毅飞')  叫做实例化对象
consolelog(hyf) //name :黄毅飞

```

## 继承

---
```js

class Person{
    // constructor 是默认的方法 不设置也会存在，这个方法，在实例化对象的时候会立即执行
    constructor(name,age){
        this.name = name
        this.age = age
    }
    //class 内部只能定义方法 方法之间不能使用逗号 ,
    sayName(){
        console.log(`my name is ${this.name}`)
        console.log(`my age is ${this.age}`)
    }
}
class Man extends Person{
    constructor(name,age,tall) {
        super(name,age)
        // 必须填super
        //实例化一个类的时候，传递的参数首先要传递给 这个类的constructor 方法，然后super 里面的参数传递给，继承的父类constructor
        this.tall = tall
    }
    say(){
        console.log("hello"); 
    }
}
let zzt = new Man('黄毅飞','18','190')
//new 加类名字加括号  new Preson('黄毅飞')  叫做实例化对象
zzt.sayName()  //my name is 黄毅飞
console.log(zzt);

```

## module

### 导出

命名导出  导入的时候必须使用相同的名字  

```js
-text.js
    let a =100
    let b =101
    let c =102
    export let a =10 //导出
    export {a,b,c} //导出
    // export {a as aa} //导出 a  重命名为 aa  
-index.js
    import {a} from "./text.js"         //导入
    import {a as aa } from "./text.js"  //导入 a 重命名为 aa
    import * as obj from "./text.js"         //导入所有导出的 放入 obj 变量内
    console.log(obj.a) //100

---
默认导出
默认导出 和命名导出可以同时存在
```js
export default a
```
导出多个
```js
export default {a:a,b:b,c:c}
```


导入时可以随便命名
import xx from "./text";

```


## ajax(同步 异步) 
