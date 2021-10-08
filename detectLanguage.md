# detectLanguage

?>  检测当前用户的首选语言

>  使用`navigationlanguage.language
> 
> 省略第二个参数，`defaultlang`，使用`'en-US'`作为默认语言代码。

```js
	const detectLanguage = (defaultLang = 'en-US') =>  navigator.language || (Array.isArray(navigator.languages) && navigator.languages[0]) || defaultLang;
```

#### 示例

```js
	detectLanguage(); // 'zh-CN'
```