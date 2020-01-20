<h1>perspective與backface的使用</h1>

[toc]

---

## perspective-origin 屬性

指定透視點的位置

1. 語法

perspective-origin: x-axis y-axis;

3. 默認值

perspective-origin: 50% 50%;


默认情况下，消失点位于元素的中心，但是可以通过设置perspective-origin属性来改变其位置


## backface-visibility 屬性

指定元素背面面向用戶時是否可見

1. 語法

backface-visibility: visible | hidden;

2. 默認值

backface-visibility: visible;


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