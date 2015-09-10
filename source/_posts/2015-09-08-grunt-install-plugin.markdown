---
layout: post
title: "grunt install plugin"
date: 2015-09-08 12:05:58 +0800
comments: true
categories: grunt
---
## 安裝 contrib-concat 套件

### 1.Insatll Plugin
[contrib-concat](https://www.npmjs.com/package/grunt-contrib-concat) 的功能是用來合併檔案

    $ npm install grunt-contrib-concat --save-dev

### 2.Init Config
    #Gruntfile.js
    module.exports = function(grunt) {

      grunt.initConfig({
        concat: {
          options: {
            // separator: ';',
          },
          dist: { // dist 可以是任何值
            src: ['js/1.js', 'js/2.js'],
            dest: 'build/script.js',
          },
        },
      });
      grunt.loadNpmTasks('grunt-contrib-concat');

    };

###### 執行前 目錄結構
     ├── grunt
     ├── js
     │   ├── 1.js
     │   └── 2.js
     ├── node_modules
     │   └── *...
     ├── Gruntfile.js
     ├── package.json

### 3.Run
    $ grunt concat

### 4.Result
執行後會產生 build 目錄且底下有一個 script.js(1.js與2.js合併)

###### 執行後 目錄結構
     ├── grunt
     ├── build
     │   └── script.js
     ├── js
     │   ├── 1.js
     │   └── 2.js
     ├── node_modules
     │   └── *...
     ├── Gruntfile.js
     ├── package.json


### 5.Modify
再加上css

    grunt.initConfig({
      concat: {
        js: {
          src: ['js/1.js', 'js/2.js'],
          dest: 'build/script.js',
        },
        css: {
          src: ['css/main.css', 'css/theme.css'],
          dest: 'build/style.css',
        },
      },
    });

###### 執行前 目錄結構
    ├── grunt
    ├── js
    │   ├── 1.js
    │   └── 2.js
    ├── css
    │   ├── main.css
    │   └── theme.css
    ├── node_modules
    │   └── *...
    ├── Gruntfile.js
    ├── package.json


### 6.Run Again
    $ grunt concat

###### 執行後 目錄結構
    ├── grunt
    ├── build
    │   ├── script.js
    │   └── style.css
    ├── js
    │   ├── 1.js
    │   └── 2.js
    ├── css
    │   ├── main.css
    │   └── theme.css
    ├── node_modules
    │   └── *...
    ├── Gruntfile.js
    ├── package.json
