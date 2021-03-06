# 浏览器兼容

浏览器常见的兼容往往是 DOM 操作和 CSS 的表现上，CSS 我们可以通过加上厂商的前缀来得到支持，DOM 我们可以判断方法的有无来像下兼容，比如你要获取一个元素的所有的子元素，那么原生 JS 就有方法来支持

```js
element.children
```

但是 `children` 只支持 IE9 及以上的浏览器，所以我们要兼容它那么只能用 `childNodes`，但是 `childNodes` 返回的并不是元素而是节点，所以我们还要在这些节点中筛选出 `nodeType` 为1的节点

常见的 DOM 兼容：

* `children`
* `firstElementChild`
* `innerText` (低版本的 FF 浏览器不支持 `innerText` 但是支持 `textContent`)

常见的 CSS 兼容：

* `opacity` (IE9 以下的浏览器 `filter: alpha(opacity=xx)` )
* `盒子模型`

CSS 的兼容我们可以通过 hack 写法（我没写过）和加浏览器厂商前缀来支持，并且可以初始化演示来尽量规避浏览器渲染的差异化

浏览器 | 前缀
-|-
google/Safari|-webkit-
FF|-moz-
Opera|-o-
IE|-ms-

JS 有 jQuery 库可以来实现规避兼容写法

