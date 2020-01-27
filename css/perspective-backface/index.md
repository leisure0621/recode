<h1>perspective與backface的使用</h1>

[toc]

@import "../../initial.css"

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