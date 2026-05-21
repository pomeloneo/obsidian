# EventHub

\#J#

- 首先确定eventHub支持的API
    
    1. 支持on
    
    1. 支持emit
    
    1. 支持off
    
    1. 支持once
    

具体实现请看源码

实现的大体思路

1. on是事件注册, 也就是订阅

1. Emit是事件触发, 也就是发布

1. off解绑事件注册

1. once注册只执行一次的事件

**源码地址** [源码地址](https://github.com/echoheart/blog-source-code/blob/master/src/eventHub/index.ts)