# 导航 tabs

## SVG 工作流

SVG 直接粘贴到 html 中，是最佳的 svg 使用策略。  
但是，网上下载的 svg 图标会有一些代码是 HTML 不兼容的，所以要用

```js
npm i -g svgo
svgo book.svg
```

使用 svgo 优化一下，然后把 newBook.svg 中的代码粘贴到 footer 中使用即可。

## 使用 active-class 进行高亮切换

https://router.vuejs.org/zh-cn/api/router-link.html
