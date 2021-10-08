# addDaysToDate

?> 从给定日期计算`n`天的日期，返回其字符串表示形式

> 使用 `new Date()` 从第一个参数创建一个日期对象。
>
> 使用`Date.prototype.getDate()` 和`Date.prototype.setDate()` 将`n`天添加到给定日期。
>
> 使用`Date.prototype.toISOString()` 返回`yyyy-mm-dd` 格式的字符串。


```js
	const addDaysToDate = (date, n) => {
	  const d = new Date(date);
	  d.setDate(d.getDate() + n);
	  return d.toISOString().split('T')[0];
	};
```

#### 示例

```js
	addDaysToDate('2020-10-15', 10); // '2020-10-25'
	addDaysToDate('2020-10-15', -10); // '2020-10-05'
```