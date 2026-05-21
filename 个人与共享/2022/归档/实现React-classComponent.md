# 实现React-classComponent

\#React#

## 简介

同functionComponent相比, classComponent更复杂 functionComponent只需要实现render功能, 而classComponent需要功能更多, 考虑的更多

- 支持声明周期

- 支持setState状态更新🤔🤒🥳🤩🤯🤬🤥😥🤠🤞🏻👶

## 判断function or class

开始之前很重要的一点就是如果区别分出functionComponent还是classComponent, 对于typeof的返回结果来看两者都返回function

根据这个结果无法得出结论

第一种方法: 可以利用class的特性来判断, 由于是class, 所以不能直接执行, 必须使用new操作符来执行, 利用这一点可以判断出结果, 这种操作必须抛出异常才可以成功, 但是抛出的异常可能不是有没有使用new操作符来操作class, 可能是别的原因, 所以这种方法不准确存在风险, 而且由于判断需要函数必须执行, 这种执行也有可能带来副作用

第二种方法: 可以利用Function.prototype.toString来返回class的内部信息, 但是这种方法的缺点是由于class是ES6新添加的, 可能会被babel装换成函数, 所以不准确

第三种方法: 类组件classComponent都必须继承制React.Component, 所以可以在React.Component.prototype上添加特殊表示来判断是否是类组件

看如下代码 假设Component就是React.Component

```
class Component {}Component.prototype.isReactComponent = true;function isClass(type) {  return (    Boolean(type.prototype) &&    Boolean(type.prototype.isReactComponent)  )}class Link extends Component {}
```

## mountComposite支持类组件

完整代码

```
function Button(props) {  return {    type: ‘button’,    props: {      class: ‘btn’,      children: [props.text]    }  }}function createElement(type, props, …args) {  const children = [].concat(…args);  props.children = children;  return {    type,    props  }}function mount(element) {  if (typeof element === ‘string’) {    return mountText(element);  }  if (typeof element.type === ‘function’) {    return mountCompositeElment(element);  }  return mountDOMElement(element);}function mountDOMElement(element) {  const type = element.type;  const props = element.props;  let children = props.children || [];  console.log(children)  children = children.filter(Boolean);  //  过滤empty  const node = document.createElement(type);  Object.keys(props).forEach((propName) => {    if (propName !== 'children') {      node.setAttribute(propName, props[propName])    }  })  //  递归渲染  children.length > 0 && children.forEach((childElement) => {    let childNode = null;    childNode = mount(childElement);    node.appendChild(childNode);  })  return node;}function mountText(text) {  return document.createTextNode(text)}function mountCompositeElment(element) {  const {type, props} = element;  const children = props.children;  if (isClass(type)) {    const instance = new type();    instance.props = props;    hooks(instance, 'componentWillMount');    element = instance.render();  } else {    element = element.type(element.props);  }  return mount(element);}function isClass(type) {  return (    Boolean(type.prototype) &&    Boolean(type.prototype.isReactComponent)  )}function hooks(instance, name, ...args) {  instance[name] && instance[name].apply(instance, args);}class Component {}Component.prototype.isReactComponent = true;class Link extends Component {  componentWillMount() {    console.log('componentWillMount');  }  render() {    console.log('render');    const {children} = this.props;    return {      type: 'a',      props: {        href: 'www.baidu.com',        children      }    }  }  // 对应的JSX形式  // render() {  //   return (  //     <a href=“http://www.baidu.com”>{children}</a>  //   )  // }}const Element = createElement(  ‘a’,  {    href: ‘www.baidu.com’  },  createElement(Button, {text: ‘button one’}),  createElement(Button, {text: ‘button two’}),  createElement(Link, {}, ‘百度’))// 对应的JSX形式// const Element = (//   <a href=“www.baidu.com”>//     <Button text=“button one”/>//     <Button text=“button two”/>//     <Link>百度<Link/>//   </a>// )const node = mount(Element)console.log(node);document.body.appendChild(node);
```