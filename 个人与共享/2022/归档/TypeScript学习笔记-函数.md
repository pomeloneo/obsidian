# TypeScript学习笔记-函数

\#T#

1. 为函数增加类型

```
let myAdd: (x: number, y: number) => number
    = function(x: number, y: number): number { return x + y; };
let myAdd: (baseValue: number, increment: number) => number
    = function(x: number, y: number): number { return x + y; };
```

只要参数类型是匹配的，那么就认为它是有效的函数类型，而不在乎参数名是否正确。

1. 可选参数和默认参数

```
function buildName(firstName: string, lastName?: string) {
    // ...
}
function buildName(firstName: string, lastName = "Smith") {
    // ...
}
```

如果是可选参数, 如果没有传入对应的参数, 那么该参数就是undefined

如果是默认参数,如果没有传入对应的参数,那么该参数就是默认的写好的那个参数值

1. 剩余参数

```
function buildName(firstName: string, ...restOfName: string[]) {
  return firstName + " " + restOfName.join(" ");
}

let employeeName = buildName("Joseph", "Samuel", "Lucas", "MacKinzie");
function buildName(firstName: string, ...restOfName: string[]) {
  return firstName + " " + restOfName.join(" ");
}

let buildNameFun: (fname: string, ...rest: string[]) => string = buildName;
```

1. 重载

ts只支持参数类型不同的重载不支持参数个数不同的重载

```
function add(a: number, b: number): number
function add(a: string, b: string): string
function add(a, b) {
  console.log(a + b)
  return a + b;
}

add(1, 1);
add('1', '1');
```