# debounce

?> 异步防抖函数 - 创建一个返回承诺的去抖动函数，但延迟调用所提供的函数，直到自上次调用以来至少经过了 `ms` 毫秒。
在此期间返回的所有promise都将返回相同的数据。

> 每次调用 debounced 函数时，使用 `clearTimeout()` 清除当前挂起的超时，并使用 `setTimeout()` 创建一个新的超时，该超时延迟调用函数，直到至少经过 `ms` 毫秒。
> 
> 使用 `Function.prototype.apply()` 将 `this` 上下文应用到函数并提供必要的参数。
>
> 创建一个新的 `Promise` 并将其 `resolve` 和 `reject` 回调添加到 `pending` promises堆栈中。
>
> 当`setTimeout` 被调用时，复制当前堆栈（因为它可以在提供的函数调用和它的分辨率之间改变），清除它并调用提供的函数。
>
> 当提供的函数解析/拒绝时，使用返回的数据解析/拒绝堆栈中的所有承诺（在调用函数时复制）。  
>
> 省略第二个参数 `ms`，将超时设置为默认值 `0` ms。

```js
	const debouncePromise = (fn, ms = 0) => {
	  let timeoutId;
	  const pending = [];
	  return (...args) =>
	    new Promise((res, rej) => {
	      clearTimeout(timeoutId);
	      timeoutId = setTimeout(() => {
	        const currentPending = [...pending];
	        pending.length = 0;
	        Promise.resolve(fn.apply(this, args)).then(
	          data => {
	            currentPending.forEach(({ resolve }) => resolve(data));
	          },
	          error => {
	            currentPending.forEach(({ reject }) => reject(error));
	          }
	        );
	      }, ms);
	      pending.push({ resolve: res, reject: rej });
	    });
	};
```

#### 示例

```js
	const fn = arg => new Promise(resolve => {
	  setTimeout(resolve, 1000, ['resolved', arg]);
	});
	const debounced = debouncePromise(fn, 200);
	debounced('foo').then(console.log);
	debounced('bar').then(console.log);
	// 将返回['resolved', 'bar']两次
```