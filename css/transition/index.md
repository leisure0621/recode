<h1>transition过渡的应用</h1>

[toc]

---

## transition-property 属性

<h4>定义</h4>

指定应用过渡的属性名称

<h4>用法</h4>

transition-property: none | all | IDENT;

none表示没有过渡，all表示所有可被动画的属性都表现出过渡的动画，IDENT表示指定的属性才使用过度动画


```css
transition-property: font-size;
```

## transition-duration 动画时间

<h4>定义</h4>

动画过渡所需的时间(单位可用秒(s)或毫秒(ms))

<h4>用法</h4>

```css
transition-duration: 10s, 30s, 230ms;
transition-duration: inherit;
transition-duration: initial;
transition-duration: unset;
```

## transition-timing-function 速度曲线

<h4>定义</h4>

通过transition-property定义被过渡的属性，每个timing-function建立[加速度曲线](https://www.jianshu.com/p/d999f090d333)，并在定义之后使用到每个css属性的过渡。

<h4>用法</h4>

```css
transition-timing-function: ease; /* 平滑过渡，等同于贝塞尔曲线（0.25,0.1,0.25,0.1） */
transition-timing-function: ease-in; /* 由慢到快，等同于贝塞尔曲线（0.42,0.0,1.0,1.0） */
transition-timing-function: ease-out; /* 由快到慢，等同于贝塞尔曲线（0.0,0.0,0.58,1.0） */
transition-timing-function: ease-in-out; /* 由慢到快再到慢，等同于贝塞尔曲线（0.42,0.0,0.58,1.0） */
transition-timing-function: linear; /* 线性过渡，等同于贝塞尔曲线（0.0,0.0,1.0,1.0） */
transition-timing-function: cubic-bezier(0.1, 0.7, 1.0, 0.1); /* 贝塞尔曲线，又称三次贝赛尔。主为生成速度曲线的函数 */
transition-timing-function: step-start; /* 等同于steps（1，start） */
transition-timing-function: step-end; /* 等同于steps（1，end） */
transition-timing-function: steps(4, end);/* 第一项参数须为正整数 第二项参数可为start或end(默认end)指定每个步骤的值发生变化的时间点 */

transition-timing-function: ease, step-start, cubic-bezier(0.1, 0.7, 1.0, 0.1);

transition-timing-function: inherit;
```

## transition-delay 延迟动画

<h4>定义</h4>

延迟一段时间后才开始执行动画

<h4>用法</h4>

```css
transition-delay: 10s, 30s, 230ms;
```

## transition 动画缩写

<h4>定义</h4>

以上几种transition的缩略写法，可只写过渡时间(ex. `transition: 0.3s;`) 。

<h4>用法</h4>

```css
transition: property duration timing-function delay; /* 属性名 过渡时间 速度曲线 延迟时间*/
```

## 结论

transition在使用的时候一定要有事件(事件的点击、属标的经过等)，其中也可设置过渡时间、速度曲线、动画延迟执行。

此属性广泛用在动画触发上(起码动画时间的设置须熟悉)，须熟悉(通常配合transform、animation、颜色等的过渡使用)。

但在应用时有时页面动画过多会造成页面画面抖动，此时就需要配合使用[硬件加速(will-change)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/will-change)，但此属性也不是万用的，仍须审慎使用(用的过多会使机器过渡消耗资源，且此功能只要使用了，就会将对应的优化存在内存当中)。

<h2>参考文献</h2>

1. [实用的 CSS — 贝塞尔曲线(cubic-bezier)](https://www.jianshu.com/p/d999f090d333)
2. [MDN transition](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transition)
3. [CSS3 动画 Transition, Animation, Transform 基础 [笔记]](https://adon988.logdown.com/posts/4729740-css3-animation-notes)

<style>
    /* 额外调整 */
    pre[class*="language-"] {
      background: rgba(0, 0, 0, 0) !important;
      box-shadow: 0px 0px 3px rgb(222, 222, 222);
      border-left: 3px solid rgba(0, 150, 136, 1);
      border-radius: 0 !important;
    }

    pre[class="language-game-select"] * {
      color: #d42b2b !important;
    }

    .g-hr {
      border-bottom: 1px dashed rgba(0, 150, 136, 1);
      margin-top: 5rem;
      margin-bottom: 5rem;
      height: auto;
      background-color: transparent;
    }

    html body {
      font-family: 'Microsoft YaHei', "Helvetica Neue", Helvetica, "Segoe UI", Arial, freesans, sans-serif !important;
    }

    .g-img {
      text-align: center;
    }

    .g-img img {
      border: 1px solid #d6d6d6;
      border-radius: 8px;
    }
</style>