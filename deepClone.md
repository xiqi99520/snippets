# deepClone

?> 创建深拷贝对象

> 使用递归。
> 
> 检查传递的对象是否为 `null`，如果是，则返回 `null`。
>
> 使用 `Object.assign()` 和一个空对象 (`{}`) 来创建原始对象的浅层克隆。
>
> 使用`Object.keys()` 和`Array.prototype.forEach()` 来确定需要深度克隆的键值对。
>
> 如果对象是`Array`，则将`clone` 的`length` 设置为原始的长度，并使用`Array.from(clone)` 创建一个克隆。

```js
	const deepClone = obj => {
	  if (obj === null) return null;
	  let clone = Object.assign({}, obj);
	  Object.keys(clone).forEach(
	    key =>
	      (clone[key] =
	        typeof obj[key] === 'object' ? deepClone(obj[key]) : obj[key])
	  );
	  if (Array.isArray(obj)) {
	    clone.length = obj.length;
	    return Array.from(clone);
	  }
	  return clone;
	};
```

#### 示例

```js
	const a = { foo: 'bar', obj: { a: 1, b: 2 } };
	const b = deepClone(a); // a !== b, a.obj !== b.obj
```