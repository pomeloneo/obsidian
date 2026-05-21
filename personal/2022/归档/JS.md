# JS

\#interview 1. ES6掌握了哪些语法

1. Promise, Promise.all, Promise.race, Class具体怎么用

1. 手写函数防抖, 函数节流

1. 手写Ajax

1. 闭包/立即执行函数分别是什么

1. 什么是JSONP, CORS, 跨域

1. async/await是什么 如何捕获异常

1. 如何实现深拷贝 递归 对象类型的判断 检查循环引用(环) 不能拷贝原型

1. 如何用正则实现tirm()

```
function tirm(str) {    return str.replace(/^\s+|\s+$/, ‘’)}
```

1. 不用class如何实现继承

```
function Animal() {    this.name = ‘Animal’}Animal.prototype.move = function move(){}function Dog() {    Animal.apply(this, arguments)    this.age = 18;}let fn = function(){}fn.prototype = Animal.prototype;Dog.prototype = new fn()Dog.prototype.constrctor = Dog;Dog.say = function (){}
```

1. 数组去重 使用hash 使用Set 使用WeakMap

1. 手写Promise