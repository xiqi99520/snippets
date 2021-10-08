# chunk

?> 将数组块分成指定大小的更小的数组

> 使用 `Array.from()` 来创建一个新的数组，它适合将要生成的块的数量。
>
> 使用 `Array.prototype.slice()` 将新数组的每个元素映射到一个长度为 `size` 的块。
>
> 如果原始数组不能均匀分割，则最终块将包含剩余元素。

```js
	const chunk = (arr, size) => Array.from({ length: Math.ceil(arr.length / size) }, (v, i) => arr.slice(i * size, i * size + size));
```

#### 示例

```js
	chunk([1, 2, 3, 4, 5], 2); // [[1, 2], [3, 4], [5]]
```