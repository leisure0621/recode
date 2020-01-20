<h1>CSS 垂直置中</h1>

[toc]

---

## vertical-align 用法

vertical-align，此元素为垂直对齐元素。仅对行内元素(span、table单元格)生效、块级元素(p)是不生效的。


```html
<style>
    .main {
        height: 200px;
        width: 100%;
        border: 1px solid #ddd;

        /* 父元素也需设置为表格 */
        display: table;
    }

    .main>div {
        /* 水平居中 */
        text-align: center;
        /* 单元格设置 */
        display: table-cell;
        border-right: 1px solid #ddd;
    }

    .main>div:last-child {
        border-width: 0px;
    }

    .baseline {
        vertical-align: baseline;
    }

    .top {
        vertical-align: top;
    }

    .middle {
        /* 垂直居中 */
        vertical-align: middle;
    }

    .bottom {
        vertical-align: bottom;
    }
</style>
<div class="main">
    <div class="baseline">
        baseline
    </div>
    <div class="top">
        top
    </div>
    <div class="middle">
        middle
    </div>
    <div class="bottom">
        bottom
    </div>
    <div class="default">
        default
    </div>
</div>
```

<table>
    <tbody>
        <tr>
            <td style="vertical-align: baseline">baseline</td>
            <td style="vertical-align: top">top</td>
            <td style="vertical-align: middle">middle</td>
            <td style="vertical-align: bottom">bottom</td>
            <td>
                <p>default</p>
            </td>
        </tr>
    </tbody>
</table>


## 单行垂直居中

```html
<style>
* {padding:0px;margin:0px;}

div {
    height: 400px;
    width: 100pxl
    border: 1px solid #ddd;
    line-height:400px;
    text-align: center;
}
</style>

<div>
    <p>line-height</p>
</div>
```

## 多行垂直居中

```html
<style>
    .main {
        height: 200px;
        width: 100%;
        border: 1px solid #ddd;

        /* 父元素也需设置为表格 */
        display: table;
    }

    .main>div {
        /* 水平居中 */
        text-align: center;
        /* 单元格设置 */
        display: table-cell;
        border-right: 1px solid #ddd;
    }

    .main>div:last-child {
        border-width: 0px;
    }

    .middle {
        /* 垂直居中 */
        vertical-align: middle;
    }
</style>
<div class="main">
    <div class="middle">
        <p>middle1</p>
        <p>middle2</p>
        <p>middle3</p>
        <p>middle4</p>
        <p>middle5</p>
    </div>
</div>
```

<div class="main" style="display: table;height: 200px;width: 100%;border: 1px solid #ddd;">
    <div class="middle" style="display: table-cell;text-align: center;vertical-align: middle;">
        <p style="margin:0;">middle1</p>
        <p style="margin:0;">middle2</p>
        <p style="margin:0;">middle3</p>
        <p style="margin:0;">middle4</p>
        <p style="margin:0;">middle5</p>
    </div>
</div>

## 结论

1. line-height方法虽然好用，但仅限于一行。
2. 如果要区块内的多行同时垂直置中则还是要使用vertical-align(要注意仅能用在**行内元素**、与**单元格**)。

<h2>参考文献</h2>

1. [mdn vertical-align](https://developer.mozilla.org/zh-CN/docs/Web/CSS/vertical-align)