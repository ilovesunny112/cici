---
layout: post
title:  "Javascript 不完全函数栗子"
date:   2018-06-02 22:55:02 +0800
categories: Javascript
---
Javascript 不完全函数非常有趣，如果利用恰当 可以提高开发效率。 举个栗子：

 
```js
function array(a,n){
	return Array.prototype.slice.call(a,n||0)
}


function partialLeft(f/*, 多参数*/){
	var args = arguments
	return function(){
		var a = array(args,1)
		a = a.concat(array(arguments))
		return f.apply(this,a)
	}
}

function partialRight(f/* 多参数...*/){
	var args = arguments;
	return function(){
		var a = array(arguments)
		a = a.concat(array(args,1))
		return f.apply(this, a)
	}
}

function partial(f/* ... args*/){
	var args = arguments
	return function(){
		var a = array(args,1)
		var i = 0, j =0;
		for(;i<arguments.length;i++){
			if(a[i] === undefined) a[i] = arguments[j++]
		}
		a = a.concat(array(arguments,j))

		return f.apply(this,a)
	}
}



// 举个栗子
var f = function(x,y,z){
	return x * (y-z)
}

// let's try it

var a1 = partialLeft(f,2)(3,4) //=> 2*(3-4)

var a2 = partialRight(f,2)(3,4) // => 3*(4-2)

var a3 = partial(f,undefined,2)(3,4)//=> 3*(2-4)

```


待续...





 

 



[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
