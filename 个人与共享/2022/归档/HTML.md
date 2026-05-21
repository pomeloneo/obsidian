# HTML

\#interview

1. **如何理解html语义化的** 举例回答 抽象问题具体化: 我平时写代码文章段落使用p标签, 标题使用h1-h6, 斜体使用i标签, 强调使用em标签, 加粗使用strong标签, 独立文章内容使用artical, 一个区域使用section, 侧边栏aside, 为了更好地seo, 为了就算丢失css的情况下也能展示良好的内容结构 便于团队成员维护代码

- 荒野阶段后台开发写html使用table布局

- 美工阶段 div + css来布局 不够语义化

- 前段阶段 使用语义化标签来写html 更专业 选择正确的标签来描述正确的内容

1. **meta viewport怎么用 怎么写**

```
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
```

控制页面在移动端不缩小不放大, 由于一开始web页面都是在pc显示的, 后来iphone推出3gs, 页面就不仅仅在pc展示了, 也要在移动端展示, iphone就想出一个办法, 将手机模拟成980px, 页面缩小, 后来智能手机普及, 这个功能基本就不需要了, 所以就有了这样一个标签告诉手机浏览器不要缩小我的页面 3. **用过哪些html5标签** header main footer article section内容相关的标签 canvas video audio