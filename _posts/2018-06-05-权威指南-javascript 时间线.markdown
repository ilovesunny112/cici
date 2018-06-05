---
layout: post
title:  "Javascript 页面加载时间线"
date:   2018-06-05 16:43:02 +0800
categories: Javascript RegExp
---
# Javascript 权威指南 页面加载时间线

1. Web 浏览器创建 Document 对象，并且开始解析 Web 页面，解析 HTML 元素和它们的文本内容后 添加 Element 对象和 Text 节点到文档中。 这个阶段 document 的 readyState 属性是 loading。
2. 当 HTML 解析器遇到 没有 async 和 defer 属性的 \<script\> 标签时，会把这些元素添加到文档中，然后执行内部或者外部的脚本。这些脚本同步执行，并且在脚本下载和执行时解析器会暂停。 这样脚本 如果有 document.write 可以把文字插入到输入流中。 解析器恢复时，这些文本会成为文档一部分。同步脚本可以看到自己元素 和 它之前的文档内容。
3. 当解析器 遇到设置了 async 属性的 \<script> 标签时，它开始下载脚本文本，同时继续解析文档。脚本会在下载完成后尽快执行，但是解析器没有停下来等它下载。异步脚本禁止使用 document.write 方法。他们可以看到自己 script 元素和它之前所有文档元素，并且可能或者干脆不可能访问其他的文档内容。 
4. 当文档完成解析，document.readyState 属性 变成 "interactive"
5. 所有有 defer 属性的脚本，会按它们出现在文档里的顺序执行。 异步脚本可能也会在这个事件执行。 延迟脚本能访问完整文档树，禁止使用 document.write 方法。
6. 浏览器在 Document 对象上触发 DOMContentLoaded 事件。 标志着程序执行 从同步脚本执行 转换到 异步事件驱动 阶段。 但要注意，这时可能还有异步脚本没有执行完成。 
7. 这时， 文档已经完全解析完成，但是浏览器可能在等待其他内容载入，如图片等。 所有这些载入完成时，并且异步脚本完成载入和执行。 document.readyState 属性改变为 "complete"， Web 浏览器触发 window 对象上的 load 事件。
8. 从此开始，会调用异步事件，异步响应用户输入事件，网络事件，计时器过期等。





待续...





 

 



[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
