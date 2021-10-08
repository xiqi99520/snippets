# average

?> 计算两个或多个数字的平均值

> 使用 `Array.prototype.reduce()` 将每个值添加到累加器中，并使用值 `0` 进行初始化。
>
> 将结果数组除以其长度。

```js
	const average = (...nums) => nums.reduce((acc, val) => acc + val, 0) / nums.length;
```

#### 示例

```js
	average(...[1, 2, 3]); // 2
	average(1, 2, 3); // 2
```