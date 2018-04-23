```
function sub(a,b){
    console.log(a+b)
}
module.exports = sub  //导出

let fun = require('./home.js')  //导入
let a = 10
let b = 20
fun(a,b)
```
核心模块 第三方模块 自定义模块  
核心模块 导入方式  require("模块名")  
第三方模块 导入方式  require("模块名")  
自定义模块 导入方式  需要自己导入导出  module.exports = sub  

