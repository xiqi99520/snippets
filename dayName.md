# dayName

?> 从`Date` 对象获取工作日的名称

> 使用`Date.prototype.toLocaleDateString()` 和`{ weekday: 'long' }` 选项来检索工作日。
>
> 使用可选的第二个参数获取特定于语言的名称或省略它以使用默认语言环境。

```js
	const dayName = (date, locale) => date.toLocaleDateString(locale, { weekday: 'long' });
```

#### 示例

```js
	dayName(new Date()); // 'Saturday'
	dayName(new Date('09/23/2020'), 'de-DE'); // 'Samstag'
```