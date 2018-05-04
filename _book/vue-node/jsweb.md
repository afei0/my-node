# JS 操作页面

本节来明确一点，不用 css 和 html ，单靠 JS ，也一样能渲染出页面来的。

## JS 添加 html 标签和控制 CSS

##### index.html

```
<html>

<head>
</head>

<body>
  <div id="app">

  </div>

  <script>
    const el = document.getElementById('app')
    el.innerHTML = '<h1>Hello</h1>'
    el.style = 'color: red'
  </script>
</body>

</html>
```

## vuejs 的原理就是用 JS 渲染页面

##### index.html

```
<html>

<head>
</head>

<body>
  <div id="app">

  </div>

  <script src="./dist/bundle.js"></script>
</body>

</html>
```

把 index.html 中的内容剪切出来，script 标签中导入 bundle.js 。

##### dist/bundle.js

```
const el = document.getElementById('app')
el.innerHTML = '<h1>Hello</h1>'
el.style = 'color: red'
```

bundle.js 中粘贴原有的三行代码。  
这样，执行一下，可以看到红色的 Hello 依然可以渲染到页面上。

## Webpack 加载 css

Webpack 是 JS 模块打包器，css/html/图片，各种其他的格式，webpack 是默认不支持的。但是通过添加 loader 。 来把其他类型的文件翻译成 ES6 模块。于是，就能统一的打包到 bundle.js 了。

```js
Module parse failed: Unexpected token (1:5)
You may need an appropriate loader to handle this file type.
```

模块解析错误，不能识别的符号。 你可能需要一个合适的 loader 加载器来处理这样的文件类型

```js
npm i vue-style-loader css-loader
```

```
  module: {
    rules: [
      {
        test: /\.vue$/,
        loader: 'vue-loader'
      },
      // this will apply to both plain .js files
      // AND <script> blocks in vue files
      {
        test: /\.js$/,
        loader: 'babel-loader'
      },
      // this will apply to both plain .css files
      // AND <style> blocks in vue files
      {
        test: /\.css$/,
        use: [
          'vue-style-loader',
          'css-loader'
        ]
      }
    ]
  },
```
