---
layout: post
title: "Gulp Install"
date: 2015-09-15 13:53:18 +0800
comments: true
categories: gulp
---
##1.安裝

 <h6>gulp 安裝與建立都與 grunt 相似</h6>

  # 專案下執行

  產生 package.json

  `$ npm init`

  安裝非全域的 gulp 套件並更新 package.json

  `$ npm install gulp --save-dev`

##2.產生 gulpfile.js
  `$ touch gulpfile.js`

##3.建立 Task
    /**
     * gulpfile.js
     */
    gulp.task('speak', function() {
      console.log('I'm Speaking');
    });

    gulp.task('yell', function() {
      console.log('I'm YELLING');
    });

    grunt.task('both', ['speak', 'yell']);

    gulp.task('default', ['speak', 'yell']);

##4.執行 Task
    $ gulp speak
    $ gulp yell
    $ gulp both
    $ gulp