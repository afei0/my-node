改变 this 指向

bind

函数名.bing(对象)
返回一个新的函数，和原函数内部功能一样，但是函数内部this已经指向了 bind 方法的第一个参数
super

super关键字只能够以指定的形式出现在以下地点：
```js
1. class语句块内的constructor函数的定义内，例如：
  class B extends A {
    constructor(){
        super()
    }
  }
2. class语句块内的static函数的定义内，例如：class B extends A {
    static foo {
        super.test1() // 相当于A.test1.call(this)
        console.log(super.test2 === A.test2)
      }
    }
3. class语句块内的一般方法（非static或constructor函数）的定义内，例如：
  class B extends A {
    foo() {
        super.foo()
    }
  }
4. 在对象字面量的方法的定义内，例如：let a = {
    foo() {
        super.test()
      }
    }

    let b = {
        test() {
            console.log("I'm b.")
        }
    }

    Object.setPrototypeOf(a, b);
    a.foo(); // "I'm b."
```
### state
state状态，组件的state改变，组件就会重新渲染，页面也就改变了
react 组件默认有一个 state 属性，这个属性是一个对象。
在constructor内设置state，用this.state = {设置状态}
使用 setState 方法修改 state 值
两个装态来回切回，设置active = true/false,然后设置时用 非 运算符，例如：!this.state.active
setState 是异步方法(异步非阻塞，同步阻塞)
requestAanimationFrame 相当于 setTimeout(这个是根据电脑本身的性能 执行快慢)
组件内部的setInterval要定义为组件的一个属性
### 子父组件相互交互

constructor 函数内部不做设置是拿不到父组件传过来的 props 的，想要拿到，需要在 constructor 函数传一个 porps 参数，并且也需要在 super 方法内传一个参数 props ，这样就可以在 constructor 内部获取到 props
state 的值 一定要定义成常量，修改组件状态 state 只能用 setState 方法修改
### 组件的生命周期(lifecycle)

组件实例被创建和插入DOM中时调用下面四个方法：
constructor() 初始化 props 和 state
componentWillMount() 组件将要挂载
render() 渲染
componentDidMount() 组件挂载完毕
属性或状态的改变会触发一次更新，当一个组件在被重渲染时，这些方法将会被调用:
componentWillReceiveProps() 只有在修改了 props 调用
shouldComponentUpdate()组件是否应该被更新（此方法 return true 意思就是同意更新 ；return false 意思就是不同意更新）
componentWillUpdate()
render()
componentDidUpdate()
componentWillUnmount() 组件销毁和卸载后立即调用,通常用来清楚计时器和网络请求 -当你修改了 state 的时候，上述生命周期函数会被执行，除了 componentWillReceiveProps() 之外，此时在这些函数内不能修改 state
当父组件想要修改子组件的状态时，需要父组件传props 修改子组件的状态，但是props 传递的时候，上述几个生命周期函数都会被触发，但只有 componentWillReceiveProps() 这个生命周期函数可以修改 state
props 默认值： 类名.defaultProps = {}