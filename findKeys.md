# findKeys

?>  查找所提供对象中与给定值匹配的所有键。

> 使用' object. keys(obj) '获取对象的所有属性。
>
> 使用' Array.prototype.filter() '来测试每个键值对，并返回与给定值相等的所有键值。

```js
	const findKeys = (obj, val) => Object.keys(obj).filter(key => obj[key] === val);
```

#### 示例

```js
	const ages = {
	  Leo: 20,
	  Zoey: 21,
	  Jane: 20,
	};
	findKeys(ages, 20); // [ 'Leo', 'Jane' ]
```