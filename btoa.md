# btoa

?> 从 String 对象创建一个 base-64 编码的 ASCII 字符串，其中字符串中的每个字符都被视为一个二进制数据字节

> 使用二进制编码为给定的字符串创建一个 `Buffer`，并使用 `Buffer.toString('base64')` 返回编码后的字符串。

```js
	const btoa = str => Buffer.from(str,  'binary').toString('base64');
```

#### 示例

```js
	btoa('foobar'); // 'Zm9vYmFy'
```