---
layout: post
title:  "优化小记"
date:   2018-05-04 09:02:02 +0800
categories: client optimization
---
最近项目中，如何提高用户查询效率，把一些脱敏的数据在用户第一次查询的时候统统返回给客户端并缓存下来，然后接下来的查询 只在客户端中进行。 这种场景适合于数据量不大/变化不大的场景。

{% highlight JavaScript %}
[
	{
		name:"张三",
		age:28
	},
	{
		name:"李四",
		age:16
	}
]
{% endhighlight %}

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
