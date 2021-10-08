# arithmeticProgression

?> 在等差数列中创建一个数字数组，从给定的正整数开始，直到指定的限制

> 使用 `Array.from()` 创建一个所需长度的数组，`lim/n`，以及一个映射函数，用给定范围内的所需值填充它。

```js
	const arithmeticProgression  = (n, lim) => Array.from({ length: Math.ceil(lim / n) }, (_, i) => (i + 1) * n );
```

#### 示例

```js
	arithmeticProgression(5, 25); // [5, 10, 15, 20, 25]
```