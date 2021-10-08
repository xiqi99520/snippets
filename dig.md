# dig

?>  基于给定密钥获取嵌套JSON对象中的目标值

>  使用`in`运算符检查`obj`中的目标是否存在。
>
> 如果找到，返回“obj [target]`的值。
>
> 否则，否则使用`object.values（obj）`和`array.prototype.reduce（）`以递归调用每个嵌套对象上的`dig`，直到找到第一个匹配键/值对。

```js
	const dig = (obj, target) => target in obj ? obj[target] : Object.values(obj).reduce((acc, val) => {
        	if (acc !== undefined) return acc;
        	if (typeof val === 'object') return dig(val, target);
        }, undefined);
```

#### 示例

```js
	const data = {
	  level1: {
	    level2: {
	      level3: 'some data'
	    }
	  }
	};
	dig(data, 'level3'); // 'some data'
	dig(data, 'level4'); // undefined
```