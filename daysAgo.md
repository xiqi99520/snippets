# daysAgo

?> 从今天开始计算 n 天前的日期作为字符串表示

> 使用`new Date()` 获取当前日期，`Math.abs()` 和`Date.prototype.getDate()` 相应地更新日期并使用`Date.prototype.setDate() 设置为结果 `。
>
> 使用`Date.prototype.toISOString()` 返回`yyyy-mm-dd` 格式的字符串。

```js
	const daysAgo = n => {
	  let d = new Date();
	  d.setDate(d.getDate() - Math.abs(n));
	  return d.toISOString().split('T')[0];
	};
```

#### 示例

```js
	daysAgo(20); // 2021-09-16 (假设今天是：2021-10-06)
```