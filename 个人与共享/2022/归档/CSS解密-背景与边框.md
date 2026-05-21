# CSS解密-背景与边框

\#css

## 半透明边框

假设我们想给一个容器设置一层白色背景和一道半透明白色边框 , body的背景会从它的半透明框透上来 最开始的尝试可能是这样的

```
border: 10px solid hsla(0, 0, 100%, .5);background: white;
```

最终效果如下:

[![](https://www.notion.soCSS%E8%A7%A3%E5%AF%86-%E8%83%8C%E6%99%AF%E4%B8%8E%E8%BE%B9%E6%A1%86/6570666D-439C-423D-B579-E7B44A9B3A55.png)](https://www.notion.soCSS%E8%A7%A3%E5%AF%86-%E8%83%8C%E6%99%AF%E4%B8%8E%E8%BE%B9%E6%A1%86/6570666D-439C-423D-B579-E7B44A9B3A55.png)

这并不是我们想要的效果 虽然看起来并不像那么回事, 但是边框是实际存在的 其实出现问题的原因就是背景的工作原理

我们可以通过`background-clip`属性来调整上述默认行为 `background-clip`的默认值是`border-box`, 也就是意味着背景会被元素的`border-box`裁剪掉 如果不希望背景侵入边框所在的范围, 则可以把值设置为`padding-box` 这样浏览器就会用内边距的外沿把背景裁剪掉

```
border: 10opx solid hsla(0, 0, 100, .5);background: white;background: padding-box;
```

效果如下:

[![](https://www.notion.soCSS%E8%A7%A3%E5%AF%86-%E8%83%8C%E6%99%AF%E4%B8%8E%E8%BE%B9%E6%A1%86/B310F3AD-575C-407B-9C34-8BBC7F418673.png)](https://www.notion.soCSS%E8%A7%A3%E5%AF%86-%E8%83%8C%E6%99%AF%E4%B8%8E%E8%BE%B9%E6%A1%86/B310F3AD-575C-407B-9C34-8BBC7F418673.png)

## 多重边框