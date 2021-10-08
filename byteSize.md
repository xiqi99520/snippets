# byteSize

?> 以字节为单位返回字符串的长度

> 将给定的字符串转换为 [`Blob` 对象]。
>
> 使用`Blob.size` 获取字符串的长度（以字节为单位）。

```js
	const byteSize = str => new Blob([str]).size;
```

#### 示例

```js
	byteSize('😀'); // 4
	byteSize('Hello World'); // 11
```