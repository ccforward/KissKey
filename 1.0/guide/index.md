## 综述

KissKey是一个简单的快捷键组件

* 版本：1.0
* 作者：chenchen
* 标签：快捷键 shortcut key
* demo：[http://gallery.kissyui.com/KissKey/1.0/demo/index.html](http://gallery.kissyui.com/KissKey/1.0/demo/index.html)


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

## 事件类型
* **down** &mdash; keydown 默认
* **up** &mdash; keyup.
* **hold** &mdash; 按下并且不松开.按下时会立即出发回调函数,并且一直重复直到keyup

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