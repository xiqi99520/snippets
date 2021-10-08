# equals

?>  在两个值之间执行深度比较，以确定它们是否等效。

> 检查两个值是否相同，如果它们都是' Date '对象，并且时间相同，使用' Date.prototype. gettime() '，或者如果它们都是非对象值，但具有等效值(严格比较)。
>
> 检查是否只有一个值是' null '或' undefined '或如果他们的原型不同。
>
> 如果以上条件都不满足，使用' Object.keys() '检查两个值是否有相同数量的键。
>
> 使用' Array.prototype.every() '来检查' a '中的每个键是否存在于' b '中，并且通过递归调用' equals() '来检查它们是否相等。

```js
	const equals = (a, b) => {
	  if (a === b) return true;
	  if (a instanceof Date && b instanceof Date)
	    return a.getTime() === b.getTime();
	  if (!a || !b || (typeof a !== 'object' && typeof b !== 'object'))
	    return a === b;
	  if (a.prototype !== b.prototype) return false;
	  const keys = Object.keys(a);
	  if (keys.length !== Object.keys(b).length) return false;
	  return keys.every(k => equals(a[k], b[k]));
	};
```

#### 示例

```js
	equals(
	  { a: [2, { e: 3 }], b: [4], c: 'foo' },
	  { a: [2, { e: 3 }], b: [4], c: 'foo' }
	); // true
	equals([1, 2, 3], { 0: 1, 1: 2, 2: 3 }); // true
```