# ES6 模块专题

传统上一个大的 JS 项目，拆分成几十个文件之后，需要分别用几十个 script 标签，导入到 html 中，这种方式是已经被淘汰的。后来 ，人们在 Nodejs 社区，发明了 commonjs 语法，也就是用 module.exports 导入，用 require 导入。但是再后来，人们发明了 ES6 模块，用 export 导出，用 import 导入，随着 ES6 的流行，ES6 模块用量上逐渐碾压 commonjs 模块。

## 为何要有模块？

模块的第一大意义在于拆分，第二大意义在于封装。例如，我在一个模块中定义和使用了一个临时的全局变量，然后在本模块内使用。那么其他的文件中即使导入了这个模块，但是模块内的临时全局变量只要是没有导出，那么其他中文件中就是不能调用的，这样就形式了良好的封装，避免了变量冲突。而 script 标签导入的形式，所有的文件中的变量默认都是全局的，就会造成严重冲突，这个是 script 标签形式的一大弊病。
ES6 模块，有两种导入导出方式，一种是命名导出（ named export ），另外一种是默认导出 （ default export ) 。

## 命名导出

命名导出的好处是一次可以从一个模块中导出多个变量。

##### main.js

```js
const sayHello = () => console.log('hello')

const myString = 'Peter'

const myFun = () => {
  sayHello()
  console.log(MySting)
}

myFun()
```

现在要把第一行和第二行拆分到独立模块之中。现在把两项内容都拷贝到 myModule.js 中，从一个模块中，导出多项内容，推荐的方式是用命名导出。

##### myModule.js

```js
export const sayHello = () => console.log('hello')

export const myString = 'Peter'
```

每个 const 之前，加上 export ，这样就导出了两个变量。在 JS 语言里面，函数就是变量。所以导出语法也没有什么区别。

##### main.js

```js
import { myString, sayHello } from './myModule'
```

命名导出之后，导入有一个局限，就是要严格按照原变量名导入（当然通过适当的语法，也可以改名，这个暂时不介绍）。同时要用中括号包裹。因为用到了 ES6 模块，所以用之前的 webpack 环境编译一下，才能运行。

## 默认导出

但是，如果我们一个模块中只导出一个变量。那么能不能把命名导出的两个限制去掉呢？恭喜，用默认导出的形式，导入使用起来就方便很多：第一，不用加中括号，第二，导入后名字任意。  
继续把上面的包含两个命名导出的 myModule.js 文件，拆分成两个用默认导出方式的 ES6 模块。

##### myString.js

```js
const myString = 'Peter'

export default myString
```

删除原有的 myModule.js ，添加 myString.js ，把 myString 进行默认导出。

##### sayHello.js

```js
const sayHello = () => console.log('hello');

export default sayHello

再添加 sayHello.js ，把 sayHello 默认导出。
// main.js
import sayHi from './sayHello'
import peter from './myString'

const myFun = () => {
  sayHi()
  console.log(peter)
}

myFun()
```

导入的时候，可以对变量进行重命名。
