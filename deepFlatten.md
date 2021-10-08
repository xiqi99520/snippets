# deepFlatten

?> 深度展平一个数组

> 使用递归。
> 
> 使用带有空数组（`[]`）和展开运算符（`...`）的`Array.prototype.concat()` 来展平数组。
>
> 递归地展平作为数组的每个元素。

```js
	const deepFlatten = arr => [].concat(...arr.map(v => (Array.isArray(v) ? deepFlatten(v) : v)));
```

#### 示例

```js
	deepFlatten([1, [2], [[3], 4], 5]); // [1, 2, 3, 4, 5]
```