# deepFreeze

?> 深度冻结对象

> 使用`Object.keys()` 获取传递对象的所有属性，使用`Array.prototype.forEach()` 迭代它们。
> 
> 在所有属性上递归调用`Object.freeze(obj)`，必要时应用`deepFreeze()`。
>
> 最后，使用`Object.freeze()` 来冻结给定的对象。

```js
	const deepFreeze = obj => {
	  Object.keys(obj).forEach(prop => {
	    if (typeof obj[prop] === 'object') deepFreeze(obj[prop]);
	  });
	  return Object.freeze(obj);
	};
```

#### 示例

```js
	const val = deepFreeze([1, [2, 3]]);

	val[0] = 3; // 修改无效
	val[1][0] = 4; // 修改无效
```