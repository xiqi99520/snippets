# averageBy

?> 使用提供的函数将每个元素映射到一个值后，计算数组的平均值

> 使用 `Array.prototype.map()` 将每个元素映射到 `fn` 返回的值。
>
> 使用 `Array.prototype.reduce()` 将每个值添加到累加器中，并使用值 `0` 进行初始化。
>
> 将结果数组除以其长度。

```js
	const averageBy = (arr, fn) => arr.map(typeof fn === 'function' ? fn : val => val[fn]).reduce((acc, val) => acc + val, 0) / arr.length;
```

#### 示例

```js
	averageBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], o => o.n); // 5
	averageBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], 'n'); // 5
```