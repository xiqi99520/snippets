# addClass

?> 将类添加到 HTML 元素

> 使用`Element.classList` 和`DOMTokenList.add()` 将指定的类添加到元素中。


```js
	const addClass = (el, className) => el.classList.add(className);
```

#### 示例

```js
	addClass(document.querySelector('p'), 'special');
```