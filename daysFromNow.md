# daysFromNow

?> 计算从今天开始的 n 天的日期作为字符串表示形式

> 使用`new Date()` 获取当前日期，`Math.abs()` 和`Date.prototype.getDate()` 相应地更新日期并使用`Date.prototype.setDate() 设置为结果 `。
>
> 使用`Date.prototype.toISOString()` 返回`yyyy-mm-dd` 格式的字符串。

```js
	const daysFromNow = n => {
	  let d = new Date();
	  d.setDate(d.getDate() + Math.abs(n));
	  return d.toISOString().split('T')[0];
	};
```

#### 示例

```js
	daysFromNow(5); // 2020-10-13 (假设今天是：2021-10-08)
```