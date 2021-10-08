# bottomVisible

?> 检查页面底部是否可见 | 检查是否一屏展示完 | 检查是否有滚动条

> 使用 `scrollY`、`scrollHeight` 和 `clientHeight` 来确定页面底部是否可见。

```js
	const bottomVisible = () => document.documentElement.clientHeight + window.scrollY >= (document.documentElement.scrollHeight || document.documentElement.clientHeight);
```

#### 示例

```js
	bottomVisible(); // true
```