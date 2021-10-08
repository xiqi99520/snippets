# debounce

?> 防抖函数 - 创建一个 debounced 函数，该函数将调用提供的函数延迟到自上次调用以来至少过去了 `ms` 毫秒
>
> 每次调用 debounced 函数时，使用 `clearTimeout()` 清除当前挂起的超时，并使用 `setTimeout()` 创建一个新的超时，该超时延迟调用函数，直到至少经过 `ms` 毫秒。
>
> 使用 `Function.prototype.apply()` 将 `this` 上下文应用到函数并提供必要的参数。
>
> 省略第二个参数 `ms`，将超时设置为默认值 `0` ms。

```js
	const debounce = (fn, ms = 0) => {
	  let timeoutId;
	  return function(...args) {
	    clearTimeout(timeoutId);
	    timeoutId = setTimeout(() => fn.apply(this, args), ms);
	  };
	};
```

#### 示例

```js
	window.addEventListener(
	  'resize',
	  debounce(() => {
	    console.log(window.innerWidth);
	    console.log(window.innerHeight);
	  }, 250)
	)
```