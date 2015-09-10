---
layout: post
title: "javascript htmlspecialchar"
date: 2015-09-03 16:01:49 +0800
comments: true
categories: javascript
---
	var _htmlspecialchars_decode = function (html) {
	    var txt = document.createElement("textarea");
	    txt.innerHTML = html;
	    return txt.value;
	};

	var _htmlspecialchars_encode = function (text) {
	  var map = {
	    '&': '&amp;',
	    '<': '&lt;',
	    '>': '&gt;',
	    '"': '&quot;',
	    "'": '&#039;'
	  };
	  return text.replace(/[&<>"']/g, function(m) { return map[m]; });
	};
來源: [http://stackoverflow.com/questions/1787322/htmlspecialchars-equivalent-in-javascript](http://stackoverflow.com/questions/1787322/htmlspecialchars-equivalent-in-javascript)