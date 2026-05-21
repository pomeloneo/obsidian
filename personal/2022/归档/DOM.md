# DOM

\#interview

1. 事件委托

1. 实现一个可拖拽的div

```
var dragging = false;var position = null;div.addEventListener(‘mousedown’, (e) => {    dragging = true;    position = [e.clientX, e.clientY]})document.addEventListener(‘mousemove’, (e) => {    const x = e.clientX;    const y = e.clientY;    const deltaX = x - position[0];    const deltaY = y - position[1];    const left = parseInt(div.style.left || 0);    const top = parseInt(div.style.top || 0);    div.style.left = left + deltaX + ‘px’;    deiv.style.top = top + deltaY + ‘px’;    position = [x, y]})document.addEventListener(‘mousemove’, (e) => {    dragging = false;})
```