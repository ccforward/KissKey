## 综述

KissKey是一个简单的快捷键组件

* 版本：1.0
* 作者：chenchen
* 标签：快捷键 shortcut key
* demo：[http://gallery.kissyui.com/KissKey/1.0/demo/index.html](http://gallery.kissyui.com/KissKey/1.0/demo/index.html)
* 浏览器支持：[http://ccforward.github.io/demos/kisskey/support.html](http://ccforward.github.io/demos/kisskey/support.html)


![KissKey](http://gtms01.alicdn.com/tps/i1/T1E9jHFotbXXbe6yUo-320-240.gif)

## 使用说明

### 初始化组件

    S.use('gallery/KissKey/1.0/index', function (S, KissKey) {
        var kissKey = new KissKey();
		
        kissKey.add({type: 'down', shortcutKeys: 'a', callback: function() { console.log('a') }});

        kissKey.start();
    })

## 基本用法

### 添加一个快捷键和回调函数
	kissKey.add({
		type: 'down', 
		shortcutKeys: 'a', 
		callback: function() { 
			console.log('a') }
	});

### 生效快捷键
	kissKey.start();

### 把快捷键添加到一个list中
	kissKey.add({
		    type: 'hold',
		    shortcutKeys: 'Shift+down',
		    callback: function() {
		        console.log('Shift+down');
		    },
		    list: 'keyList'
	});
### 生效keyList
	kissKey.start('keyList');

### 移除快捷键
	kissKey.remove({
		    type: 'hold',
		    shortcutKeys: 'Shift+down',
		    callback: function() {
		        console.log('Shift+down');
		    },
		    list: 'keyList'
	});

### 解除绑定
	kissKey.stop();

## 支持的事件类型
* **down** &mdash; keydown 默认
* **up** &mdash; keyup.
* **hold** &mdash; 按下并且不松开.按下时会立即出发回调函数,并且一直重复直到keyup

## 支持的按键
* **组合键** &mdash; Shift Ctrl Alt
* **数字字母** &mdash; 0-9 a-z(大小写不敏感)
* **特殊按键1** &mdash; Backspace, Tab, Enter, Pause, CapsLock, Esc, Space, F1—F12(有浏览器兼容性问题和系统冲突问题),
* **特殊按键2** &mdash; left(←), up(↑), right(→), down(↓) ,PageUp, PageDown, End, Home, Insert, Delete

## 标点符号和小键盘使用说明
* '?' : 问号 兼容小键盘的 "/"
* 'minus' : - 兼容小键盘
* 'plus' : + 兼容小键盘
* 'semi' : 分号 ;
* 'comma' : 逗号 ,
* 'dot' : 句号 . 兼容小键盘
* 'quot' : 引号 '
* '[' : 左中括号
* ']' : 右中括号
* '\\\' : 顿号,要两个斜线
* 'num0' ~ 'num9' :小键盘
* '`'' : 波浪号


## 绑定多个按键
	kissKey.add({
		    type: 'hold',
		    shortcutKeys: 'Shift+down,Ctrl+down',
		    callback: function() {
		        console.log('Shift+down');
		    },
		    list: 'keyList1,keyList2'
	}).start();

## 输入框输入  (不完善)TODO
	kissKey.add({
		    type: 'hold',
		    shortcutKeys: 'Shift+down',
		    enableInInput: true, //默认false
		    callback: function() {
		        console.log('Shift+down');
		    },
		    list: 'keyList'
	});




## 浏览器快捷键支持情况
* 详细支持情况戳向此处：[http://ccforward.github.io/demos/kisskey/support.html](http://ccforward.github.io/demos/kisskey/support.html)
![KissKey-support](http://pic.yupoo.com/ccking/Df4WTuzl/inSBo.jpg)



## Changelog
* 131018: 添加小键盘和特殊标点符号的支持
