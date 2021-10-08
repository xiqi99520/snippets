# chunkIntoN

?> 将数组分块为 n 个较小的数组

> 使用`Math.ceil()` 和`Array.prototype.length` 来获取每个块的大小。
>
> 使用 `Array.from()` 创建一个大小为 `n` 的新数组。
>
> 使用 `Array.prototype.slice()` 将新数组的每个元素映射到一个长度为 `size` 的块。

```js
	const chunkIntoN = (arr, n) => {
	  const size = Math.ceil(arr.length / n);
	  return Array.from({ length: n }, (v, i) =>
	    arr.slice(i * size, i * size + size)
	  );
	}
```

#### 示例

```js
	chunkIntoN([1, 2, 3, 4, 5, 6, 7], 4); // [[1, 2], [3, 4], [5, 6], [7]]
```