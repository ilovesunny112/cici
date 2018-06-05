---
layout: post
title:  "Javascript 同源策略"
date:   2018-06-05 16:43:02 +0800
categories: Javascript XHR
---
# Javascript 权威指南 同源策略

安全！！ 为了基本的安全！

同源策略是 JS 脚本能够操作哪些内容的限制。 
当使用 iframe 或者 打开多个浏览器窗口 利用脚本来进行 通信 这时候同源策略会发挥作用。 

所谓同源：同协议(protocol) + 同端口 （port） + 同域名（domain）

以上任何一个不满足 就不算是同源
注意（脚本本身来源 不算 同源策略考虑范围内，外调用脚本 主要看执行的环境是当前文档）

举个跨域脚本栗子：A 站调用了 来自 B站脚本。 该脚本可以访问 A 站全部内容。比如 该脚本打开一个窗口 同样是 A站文档，那么仍然可以访问文档。但如果该脚本打开一个 C 站文档，那么脚本无法访问 C 的文档内容。 

同源策略不只是 iframe 会涉及到， XMLHttprequest 也会受到同源策略限制。 

**不严格的同源策略**

同源策略略微有些严格，如何破解？2种方式如下：

1. 比如 doc.microsoft.com 和 msdn.microsoft.com 是 microsoft.com 下的两个域名，如果想互相进行资源共享访问，可以设置 这两个文档的 document.domain 属性   document.domain= "microsoft.com"  这样 这两个域名下的文档脚本可以互相访问另外的文档了。 
2. CORS(cross original resource sharing ) 括号里文字我猜出来的，不一定准确。 需要设置一系列包括但不限于如下请求头：Access-Cotrol-Allow-Origin:"*"
如果需要跨域传递登陆信息 还要带上 withConfidential 属性  服务器和客户端都要进行设置。 



 





待续...





 

 



[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
