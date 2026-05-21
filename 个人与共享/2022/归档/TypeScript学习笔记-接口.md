# TypeScript学习笔记-接口

\#T#

1. 接口写法

```
  interface 接口名 {
    属性名: 属性类型
  }

  interface Person {
    name: string
  }
```

接口就是描述一个对象有什么属性和方法

1. 接口的用法

```
  interface Shape {
    head: string;
    body: strin;
  }
  interface Person {
    readonly name: string;  //  只读属性
    age: number;
    shape: Shape;
    say(word: string): void;
    games?: Array<string>;  //  可选属性可有也无的属性
  }
  const person: Person = {
    name: 'li',
    age: 20,
    shape: {
      head: 'yuan',
      body: 'chang'
    },
    say(word: string) {
      console.log(word)
    }
  }
  person.say('nihao');
    person.name = 'other'   //  error
```

1. 额外的属性检查

```
interface SquareConfig {
    color?: string;
    width?: number;
}

function createSquare(config: SquareConfig): void {
    // ...
}
let mySquare = createSquare({ colour: "red", width: 100 }); //  error
```

这种类型检查会检测出接口所定义的形状和出入参数的形状是不符合的,会报错

以下的方式可以绕过类型检查, 也就是说即使传入出错也不会被检查出来

不推荐故意绕过类型检查, 可能会引发隐患

```
let mySquare = createSquare({ width: 100, opacity: 0.5 } as SquareConfig);
//  使用类型断言
interface SquareConfig {
    color?: string;
    width?: number;
    [propName: string]: string | number;
}
//  使用字符串索引签名
let squareOptions = { colour: "red", width: 100 };
let mySquare = createSquare(squareOptions);
//  它就是将这个对象赋值给一个另一个变量： 因为 squareOptions不会经过额外属性检查，所以编译器不会报错。
```

1. 定义接口描述函数

```
interface FunctionC {
  (a: number, b: number): number;
}
function fn(a: number. b: number): number {
  return a + b;
}
```

函数的接口参数名不一定要相同, 这样和上面试完全等价的除了参数名不一样之外

```
function fn(aa: number. bb: number): number {
  return aa + bb;
}
```

1. 接口可以继承

```
interface Shape {
    color: string;
}

interface PenStroke {
    penWidth: number;
}

interface Square extends Shape, PenStroke {
    sideLength: number;
}

let square = <Square>{};
square.color = "blue";
square.sideLength = 10;
square.penWidth = 5.0;
```