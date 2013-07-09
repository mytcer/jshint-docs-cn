JSHint文档汉化版
=================

## 一. 使用方式

### 用法一：作为node程序使用

##### 1. 安装jshint

	$ npm install jshint -g
	
##### 2. 命令行下用jshint检查目标文件

	// 目标文件test.js的内容
	/* jshint unused: true */
	var a = 1;
	var b = 2;
	alert(b);
	
	// 命令行下检查test.js
	$ jshint test.js
	
	// 命令行下输出的检查结果
	test.js: line 2, col 6, "a" is defined but never used.
	
	1 error
	

## 三. JSHint options

JSHint有两种类型的options：

  * enforcing -- 它们使JSHint更加严格，[详细介绍](enforcing_options.md)；

  * relaxing -- 它们用来抑制一些警告，[详细介绍](relaxing_options.md).

