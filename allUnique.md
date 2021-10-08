# allUnique

?> 检查数组中的所有元素是否唯一

> 从映射的值创建一个新的“Set”以仅保留唯一的出现。
>
> 使用 `Array.prototype.length` 和 `Set.prototype.size` 将唯一值的长度与原始数组进行比较。


```js
	const allUnique = arr => arr.length === new Set(arr).size;
```

#### 示例

```js
	allUnique([1, 2, 3, 4]); // true
	allUnique([1, 1, 2, 3]); // false
```