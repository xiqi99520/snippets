# escapeRegExp

?>  转义要在正则表达式中使用的字符串。

> 使用' String.prototype.replace() '转义特殊字符。

```js
	const escapeRegExp = str => str.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
```

#### 示例

```js
	escapeRegExp('(test)'); // \\(test\\)
```