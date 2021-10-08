# detectDeviceType

?> 检测页面是否正在移动设备或桌面上查看

> 使用正则表达式来测试`Navigator.UserAgent`属性以弄清楚设备是否是移动设备或桌面。

```js
	const detectDeviceType = () =>
	  /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
	    navigator.userAgent
	  )
	    ? 'Mobile'
	    : 'Desktop';
```

#### 示例

```js
	detectDeviceType(); // 'Mobile' or 'Desktop'
```