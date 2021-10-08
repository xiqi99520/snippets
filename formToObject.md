# formToObject

?>  将一组表单元素编码为一个“对象”。

> 使用' FormData '构造函数将HTML ' form '转换为' FormData '，并使用' array. from() '转换为数组。
>
> 使用' array .prototype.reduce() '从数组中收集对象

```js
	const formToObject = form =>
	  Array.from(new FormData(form)).reduce(
	    (acc, [key, value]) => ({
	      ...acc,
	      [key]: value
	    }),
	    {}
	  );
```

#### 示例

```js
	formToObject(document.querySelector('#form'));
	// { email: 'test@email.com', name: 'Test Name' }
```