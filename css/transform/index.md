<h1>CSS transform 属性</h1>

[toc]

---

## transform 的作用

transform 这个属性，可以让元素进行移动、旋转、缩放、倾斜。

## transform 2D转换

| 语法               | 说明                                                              | 范例                                            |
| :----------------- | :---------------------------------------------------------------- | :---------------------------------------------- |
| transform-function | 变换函数(如: scale(x,y)等)，中间用空格(` `)隔开可使用多个函数变换 | transform: translate(30px, 20px) rotate(20deg); |
| none               | 不做任何变换                                                      | transform: none;                                |

## 变换函数说明

配合使用以下函数就可做各种变化，其中deg表示变换角度，而如果使用到translate的话则可使用px或%进行偏移。

| 语法                | 说明      | 语法                                           |
| :------------------ | :-------- | :--------------------------------------------- |
| rotate()            | 旋转      | transform: rotate(0.5deg);                     |
| scale(x,y)          | 缩放      | transform: scale(2, 0.5);                      |
| skew(x,y)           | 扭曲/斜切 | transform: skew(30deg, 20deg);                 |
| matrix()            | 矩阵变换  | transform: matrix(1, 2, 3, 4, 5, 6);           |
| translate(x,y)      | 偏移      | transform: translate(120px, 50%);              |
| scale() translate() | 缩放 偏移 | transform: scale(0.5) translate(-100%, -100%); |

## 实际效果

```html
<style>
    .translate-box {
        display: flex;
    }

    .translate-box>div {
        width: calc(100%/6);
        background-color: #63a35c;
        transition: 1s;
        text-align: center;
        font-size: 14px;
    }

    .rotate:hover {
        transform: rotate(18deg);
    }

    .scale:hover {
        transform: scale(2, 0.5);
    }

    .skew:hover {
        transform: skew(30deg, 20deg);
    }

    .matrix:hover {
        transform: matrix(1, 2, 3, 4, 5, 6);
    }

    .translate:hover {
        transform: translate(120px, 50%);
    }

    .scale-translate:hover {
        transform: scale(0.5) translate(-100%, -100%);
    }
</style>
<div class="translate-box">
    <div class="rotate">transform: rotate(0.5deg);</div>
    <div class="scale">transform: scale(2, 0.5);</div>
    <div class="skew">transform: skew(30deg, 20deg);</div>
    <div class="matrix">transform: matrix(1, 2, 3, 4, 5, 6);</div>
    <div class="translate">transform: translate(120px, 50%);</div>
    <div class="scale-translate">transform: scale(0.5) translate(-100%, -100%);</div>
</div>
```

<style>
    .translate-box {
        display: flex;
    }

    .translate-box>div {
        width: calc(100%/6);
        background-color: #63a35c;
        transition: 1s;
        text-align: center;
        font-size: 14px;
    }

    .rotate:hover {
        transform: rotate(18deg);
    }

    .scale:hover {
        transform: scale(2, 0.5);
    }

    .skew:hover {
        transform: skew(30deg, 20deg);
    }

    .matrix:hover {
        transform: matrix(1, 2, 3, 4, 5, 6);
    }

    .translate:hover {
        transform: translate(120px, 50%);
    }

    .scale-translate:hover {
        transform: scale(0.5) translate(-100%, -100%);
    }
</style>
<div class="translate-box">
    <div class="rotate">transform: rotate(0.5deg);</div>
    <div class="scale">transform: scale(2, 0.5);</div>
    <div class="skew">transform: skew(30deg, 20deg);</div>
    <div class="matrix">transform: matrix(1, 2, 3, 4, 5, 6);</div>
    <div class="translate">transform: translate(120px, 50%);</div>
    <div class="scale-translate">transform: scale(0.5) translate(-100%, -100%);</div>
</div>

## 结论

其实在transform地应用中多数用到的有scale()与translateX()、translateY()。

scale()主要是在hover后的大小变换(图片/区块大小变化)，translateX()则可做类似sidebar不用时缩入画面左方，hover时才出现...等等的效果。

上面虽可使用的函数很多但大多先知道就好。

<h2>参考文献</h2>

1. [CSS transform 能旋转、倾斜、缩放变形 box](https://boohover.pixnet.net/blog/post/35341387)
1. [理解CSS3 transform中的Matrix(矩阵)](https://www.zhangxinxu.com/wordpress/2012/06/css3-transform-matrix-%E7%9F%A9%E9%98%B5/)
2. [mdn transform](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform)