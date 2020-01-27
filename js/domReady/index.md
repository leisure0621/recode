<h1>什么是 domReady ?</h1>

[toc]

@import "../../initial.css"

---

## domReady

所有的HTML都转成节点后，就叫做 DOM 树构建完毕也就是 domReady(完整说法为 DOMContentLoaded)。

> 即一个被封装的方法，用以当浏览器生成DOM树结构后就开始解析某些js代码。

## Dom 文档加载步骤

1. 解析HTML
2. 加载外部脚本(*.js)和样式表(*.css)文件
3. 解析并执行脚本
4. Dom树构建完成(DOMContentLoaded，缩写为 domReady)
5. 加载图片等外部文件
6. 页面加载完毕

## domReady的实现策略

因为实际开发中通常会有很多js代码，如果都使用window.onload的话加载速度则会很慢，故为了提升速度且也为了在构建完后触发，制定了以下策略。


1. 支持DOMContentLoaded事件的，就使用DOMContentLoaded事件。
2. 不支持的就用来自Diego Perini发现的着名Hack兼容。兼容原理大概就是通过IE中的document，documentElement.doScroll('left')来判断DOM树是否创建完毕。

使用javascript实现的方法如下。

1. 创建一个 `domReady.js`
2. 页面引用 `domReady.js`
3. 使用 `myReady` 回调函数

```js
function myReady(fn){  
    //对于现代浏览器，对DOMContentLoaded事件的处理采用标准的事件绑定方式  
    if ( document.addEventListener ) {  
        document.addEventListener("DOMContentLoaded", fn, false);  
    } else {  
        IEContentLoaded(fn);  
    }  
    //IE模拟DOMContentLoaded  
    function IEContentLoaded (fn) {  
        var d = window.document;  
        var done = false;  

        //只执行一次用户的回调函数init()  
        var init = function () {  
            if (!done) {  
                done = true;  
                fn();  
            }  
        };  
        (function () {  
            try {  
                // DOM树未创建完之前调用doScroll会抛出错误  
                d.documentElement.doScroll('left');  
            } catch (e) {  
                //延迟再试一次~  
                setTimeout(arguments.callee, 50);  
                return;  
            }  
            // 没有错误就表示DOM树创建完毕，然后立马执行用户回调  
            init();  
        })();  
        //监听document的加载状态  
        d.onreadystatechange = function() {  
            // 如果用户是在domReady之后绑定的函数，就立马执行  
            if (d.readyState == 'complete') {  
                d.onreadystatechange = null;  
                init();  
            }  
        }  
    }  
}
```

4. 实际使用方法

```html
<div id="showMsg"></div>
<script>
var msgBox = d.getElementById("showMsg");
myReady(function() {
    msgBox.innerHTML += "dom已加载！<br>";
    msgBox.innerHTML += "时间戳：" + time1 + "<br>";
});
</script>
```

## 结论

再对比下发现DomReady比onload快了2秒多，故在实际上使用的时候不应该常偷懒的仅使用 `window.onload` 去处理问题。

而是思考在一般使用的情况下如何更加提升效率，是我们在思考中所需要提升的。

<h2>参考文献</h2>

1. [在 DOM 中动态执行脚本](https://harttle.land/2017/01/16/dynamic-script-insertion.html)
2. [你不知道的 DOMContentLoaded](https://zhuanlan.zhihu.com/p/25876048)
3. [简述domready和onload事件的区别](https://www.jianshu.com/p/6b0a95cdbc7a)
4. [【js】实现DOMReady](https://www.jianshu.com/p/88b9d3874749)
5. [DOM探索之-domReady](https://www.geekjc.com/post/5c2b9a5e2b963e0f4f041aca)