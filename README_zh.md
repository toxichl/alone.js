# alone.js

[![Travis](https://img.shields.io/travis/rust-lang/rust.svg)]()
[![Travis](https://img.shields.io/badge/download-%3C1kb-red.svg)]()
[![apm](https://img.shields.io/apm/l/vim-mode.svg)]()
[![apm](https://img.shields.io/github/stars/toxichl/alone.js.svg?style=social&label=Star)]()

一个极简的运行在浏览器上的 `CommonJS` 模块加载器

## Quick Start

在你的页面中 body 中引入：

```html
<script src="https://unpkg.com/alone.js@1.0.1/dist/alone.js"></script>
```

新建两个文件 `add.js`、`index.js`, 在页面中引入：

```html
<script src="add.js"></script>
<script src="index.js"></script>
```

 `test.js`的内容：

```js
;(function () {

    function add(count) {
		return ++count;
	}
	var metadata = {
		name: 'Chen Haoli',
		words: 'Hello World!'
    }
	exports.year = '1994'
	module.exports = {
		add: add,
		metadata: metadata
	};
	// in ES6 you can write like this：module.exports = {add}

}
)()
```

`index.js`的内容：

```js
;(function () {
	
	var add = require('add')
	var data = require('metadata')
	
	console.log(add(1))   // 2
	console.log(data.name + ' says ' + data.word)   // toxichl says Hello World!
	console.log(year)   // 1994
})()
```

是不是写法和 `node.js` 的 `CommonJS` 写法很像？


## 声明

这只是一个玩具，请勿用于生产环境


