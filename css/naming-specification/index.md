<h1>CSS 命名规范</h1>

[toc]

@import "../../initial.css"

---

## 命名规范的意义

1. 可以再看见CSS就知道具体这个选择器是做什么
2. 从名子就能知道选择器在哪边使用
3. 从名称就可知道选择器间的联系

且css可以再多个页面当中使用，更好的定义css的规范能让一个团队更好的去合作并提高我们的工作效率!

## 命名方法

#### 单字命名

```css
.special{...}
```

#### 连字符命名

```css
.main-title{...}
```

#### 下滑线命名

```css
.main_title{...}
```

#### 驼峰命名

```css
.mainTitle{...}
```

#### BEM命名

```scss
// 家猫__花色--虎斑/黑白斑点
.domestic-cat{
    &__flower-color--leopard{...}
    &__flower-color--black-and-white-spot{...}
}
```

| 定义     | 说明 | 连接方式 |
| :------- | :--- | :------- |
| block    | 模块 | `-`      |
| element  | 元素 | `__`     |
| modifier | 修饰 | `--`     |

即`.domestic-cat`表示模块，`__flower-color`表示元素，`--leopard`表示修饰符

## 常用的命名方式

| 页面结构     |                   | 导航   |             | 功能   |          |
| :----------- | :---------------- | :----- | :---------- | :----- | :------- |
| 页首         | header            | 导航   | nav         | 标志   | logo     |
| 页面主体     | main              | 主导航 | mainnav     | 广告   | banner   |
| 页尾         | footer            | 子导航 | subnav      | 登录   | login    |
| 内容         | content/container | 边导航 | sidebar     | 登录条 | loginbar |
| 容器         | container         | 顶导航 | topnav      | 注册   | register |
| 导航         | nav               | 左导航 | leftdisebar | 功能区 | shop     |
| 右导航       | rightsidebar      | 菜单   | menu        | 标题   | title    |
| 侧栏         | sidebar           | 子菜单 | submenu     | >      |          |
| 栏目         | column            | 搜索   | search      | >      |          |
| 页面外围控制 | wrapper           | 标题   | title       | >      |          |
| 左右中       | left right center | 摘要   | summery     | >      |          |

## 命名空间

| 常见命名空间 | 说明                                     | 举例             |
| :----------- | :--------------------------------------- | :--------------- |
| o-           | 对象(Object)                             | .o-layout        |
| c-           | 组件(Component)                          | .c-avatar        |
| u-           | 通用工具(Utility)                        | .u-hidden        |
| t-           | 主题(Theme)                              | .t-light。       |
| s-           | 上下文或作用域(Scope)                    | .s-cms-content。 |
| is-，has-    | 表示一种状态或条件样式                   | .is-active       |
| _            | hack                                     | ._important。    |
| js-          | JavaScript 钩子                          | .js-modal。      |
| qa-          | 表示测试钩子                             |
| g-           | 布局，表示布局，类似头、尾、主题、侧栏等 |
| m-           | 模组，表示登录、注册、搜寻等较大的整体   |
| u-           | 元件，表示按钮，输入框等                 |
| f-           | 功能，使用频率较高的样式，如清除浮动     |
| s-           | 面板，例如文字色、背景色、边框色等       |
| z-           | 状态，例如hover、选中等状态              |
| j-           | 用于js获取节点使用                       |

## 总结

以css来说多使用连字符命名方式，js或其他的才使用驼峰命名法。id不要滥用，且id经常会在js上使用(id是唯一的，不能多次使用。且id优先级高于class)，主要通过id来进行文档操作。而class择适当使用即可。

假设以BEM的方式命名的话，可以让命名更清晰准确，虽然长度会增加，但在减少嵌套的过程中也可增加渲染效率。

但最終為了避免純使用`BEM`的話會造成汙染(BEM的重用性)，會配合`命名空間`來使用。

<h2>参考文献</h2>

1. [前端人员必看CSS命名规范](https://www.itread01.com/articles/1489384810.html)
2. [CSS命名规范](https://codertw.com/%E5%89%8D%E7%AB%AF%E9%96%8B%E7%99%BC/182219/)
3. [CSS 命名规范总结](https://jiandanxinli.github.io/2016-08-11.html)
4. [这些 CSS 命名规范将省下你大把调试时间](https://juejin.im/post/5a6c5881518825733201daf7)