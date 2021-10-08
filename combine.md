# combine

?> 组合两个对象数组，使用指定的键来匹配对象

> 使用带有对象累加器的 `Array.prototype.reduce()` 以根据给定的 `prop` 组合两个数组中的所有对象。
>
> 使用`Object.values()` 将结果对象转换为数组并返回。

```js
	const combine = (a, b, prop) =>
	  Object.values(
	    [...a, ...b].reduce((acc, v) => {
	      if (v[prop])
	        acc[v[prop]] = acc[v[prop]]
	          ? { ...acc[v[prop]], ...v }
	          : { ...v };
	      return acc;
	    }, {})
	 );
```

#### 示例

```js
	const x = [
	  { id: 1, name: 'John' },
	  { id: 2, name: 'Maria' }
	];
	const y = [
	  { id: 1, age: 28 },
	  { id: 3, age: 26 },
	  { age: 3}
	];
	combine(x, y, 'id');
	// [
	//  { id: 1, name: 'John', age: 28 },
	//  { id: 2, name: 'Maria' },
	//  { id: 3, age: 26 }
	// ]
```