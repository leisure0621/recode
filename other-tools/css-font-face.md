<h1>自定义 font-face</h1>

[toc]

---

## 什么是 font-face ?

font-face表示自定义文本字体，字体能用远程(http 或 https)或本地安装的进行加载

## font-face 通用模板

以后独立的文字设置可参考通用模板。

```css
@font-face {
    font-family : <customFontName>;
    src: url('filePath/customFontName.eot'); /*IE9以上浏览器*/
    src: url('filePath/customFontName.eot?#iefix' format('embedded-opentype'), /*IE6-8，使用 embedded-opentype 编码格式*/
         url('filePath/customFontName.ttf') format('truetype'), /* Safari,Android,IOS 兼容手机端*/
         url('filePath/customFontName.woff') format('woff'), /* Modern Browsers 兼容所有浏览器*/
         url('filePath/customFontName.svg#customFontName') format('svg'), /* Legacy IOS */
}
```

## font-face 用法实践

customFontName需自行下载，一般会放置font目录当中。
在使用时建议`@font-face`中`customFontName`名称与字体文件名统一，以利于使用与查找方便。

```
.
|   
+---filePath
|       customFontName.ttf
|       
|   index.html
```

在html文件当中，将代码直接放置style中就能够使用了!最后设置需使用此字型的文字即可顺利改变字型!!若有需要的话也可放至css文件当中。

```html
<style>
    @font-face {
        font-family : <customFontName>;
        src: url('filePath/customFontName.eot'); /*IE9以上浏览器*/
        src: url('filePath/customFontName.eot?#iefix' format('embedded-opentype'), /*IE6-8，使用 embedded-opentype 编码格式*/
             url('filePath/customFontName.ttf') format('truetype'), /* Safari,Android,IOS 兼容手机端*/
             url('filePath/customFontName.woff') format('woff'), /* Modern Browsers 兼容所有浏览器*/
             url('filePath/customFontName.svg#customFontName') format('svg'), /* Legacy IOS */
    }
    * {
        font-family: 'customFontName';
    }
</style>
```

## 字体网站推荐

假设下载的文字只有一种版本，则会造成站台使用时多浏览器不兼容的情形。若需下载此字体的多种档案类型则推荐至[www.fontsquirrel.com](https://www.fontsquirrel.com/tools/webfont-generator)中上传已下载的字体，并选择`expert`。

在font-format中可选择需要的字体格式，并选择`EOT Compressed`(字体为压缩版)，选完后按`Donlowad`即可下载。

## 结论

1. 字体文件与font-family自订译名称需统一，利于查找与使用。
2. 为了浏览器兼容性，建议将所需的字型档案下载全(*.ttf, *.eot, *.woff, *.svg)
3. 文件路径必须正确且可使用，否则易造成网页渲染阻塞

<h2>参考文献</h2>

1. [mdn font-face](https://developer.mozilla.org/zh-CN/docs/Web/CSS/@font-face)
2. [阻塞渲染的 CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css?hl=zh-cn)
3. [原来 CSS 与 JS 是这样阻塞 DOM 解析和渲染的](https://juejin.im/post/59c60691518825396f4f71a1)