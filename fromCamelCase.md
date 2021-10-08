# fromCamelCase

?>  从驼峰式转换字符串。

> 使用' string .prototype.replace() '将字符串分成单词，并在它们之间添加' separator '。
>
> 省略第二个参数，使用默认的' _ '分隔符。

```js
	const fromCamelCase = (str, separator = '_') => 
	str.replace(/([a-z\d])([A-Z])/g, '$1' + separator + '$2')
	    .replace(/([A-Z]+)([A-Z][a-z\d]+)/g, '$1' + separator + '$2')
	    .toLowerCase();
```

#### 示例

```js
	fromCamelCase('someDatabaseFieldName', ' '); // 'some database field name'
	fromCamelCase('someLabelThatNeedsToBeDecamelized', '-'); 
	// 'some-label-that-needs-to-be-decamelized'
	fromCamelCase('someJavascriptProperty', '_'); // 'some_javascript_property'
	fromCamelCase('JSONToCSV', '.'); // 'json.to.csv'
```