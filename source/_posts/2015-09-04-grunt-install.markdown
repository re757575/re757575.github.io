---
layout: post
title: "Grunt Install"
date: 2015-09-04 08:38:59 +0800
comments: true
categories: grunt
---
#####注意: 必須先安裝 [Node.js](https://nodejs.org/en/) (建議使用 [nvm](https://github.com/creationix/nvm "Node Version Manager") 安裝)

##1.安裝

	# 首先安裝 grunt cli 套件
	$ npm install -g grunt-cli

	# 專案下執行
	$ npm inint
	$ npm intall -S grunt

	目錄下會產生 node_modules 資料夾 與 package.json

##2.產生 Gruntfile.js
	$ touch Gruntfile.js

##3.建立 Task
	/**
	 * Gruntfile.js
	 */
	module.exports = function(grunt) {
	// $ grunt speak
	grunt.registerTask('speak', function(){
		console.log("I'm Speaking");
	});

	// $ grunt yell
	grunt.registerTask('yell', function(){
		console.log("I'm YELLING");
	});

	// $ grunt both
	grunt.registerTask('both', ['speak', 'yell']);

	// $ grunt
	grunt.registerTask('default', ['speak', 'yell']);

	};

##4.執行 Task
	$ grunt speak
	$ grunt yell
	$ grunt both
	$ grunt