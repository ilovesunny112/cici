---
layout: post
title:  "Javascript 脚本化 HTTP jsonp 的实现"
date:   2018-06-08 17:23:02 +0800
categories: Javascript jsonp
---
# Javascript 权威指南 脚本化 HTTP jsonp

beta 版本

```html
<script>
        function getJSONP(url,callback){
            var cbnum = "cb" + getJSONP.counter++;
            var cbname = "getJSONP." + cbnum;

            if(url.indexOf("?") === -1){
                url += "?jsonp="+cbname;
            }
            else{
                url += "&jsonp="+cbname;
            }

            var script = document.createElement("script")

            getJSONP[cbnum] = function(response){
                try{
                    callback(response)
                }
                finally{
                    delete getJSONP[cbnum]
                    script.parentNode.removeChild(script)
                }
            }


            script.src = url;
            document.body.appendChild(script)
        }


        getJSONP.counter = 0


        // 不知道 jquery 的 jsonp 怎么实现 
    </script>

```

待续...





 

 



[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
