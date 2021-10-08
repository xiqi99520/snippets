# functions	

?>  从对象自己的(可选继承的)可枚举属性获取函数属性名数组。

> 使用' object .keys(obj) '来遍历对象自己的属性。
>
> 如果“inherited”为“true”，使用“object . getprototypeof (obj)”也获取对象的继承属性。
>
> 使用' Array.prototype.filter() '只保留那些函数属性。
>
> 省略第二个参数' inherited '，默认情况下不包含继承的属性。

```js
	const functions = (obj, inherited = false) =>
	  (inherited
	    ? [...Object.keys(obj), ...Object.keys(Object.getPrototypeOf(obj))]
	    : Object.keys(obj)
	  ).filter(key => typeof obj[key] === 'function');
```

#### 示例

```js
	function Foo() {
	  this.a = () => 1;
	  this.b = () => 2;
	}
	Foo.prototype.c = () => 3;
	functions(new Foo()); // ['a', 'b']
	functions(new Foo(), true); // ['a', 'b', 'c']
```