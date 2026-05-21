# TypeScript类型

1. 类型的且运算 \#T#

```
interface A {
  name: string;
  age: number;
}
interface B {
  name: string;
  grade: number;
}
const c: A & B = {
  name: 'li',
  age: 10,
  grade: 60
}
```

且运算后得到的类型是必须都要满足才可以的

1. 类型的或运算

```
interface A {
  name: string;
  age: number;
}
interface B {
  name: string;
  grade: number;
}
const c: A | B = {
  name: 'li',
  age: 10,
  grade: 60
}
```

满足其中之一的类型就可以

1. 类型别名

```
interface A {
  name: string;
  age: number;
}
interface B {
  name: string;
  grade: number;
}
type AB = A & B;
const c: AB = {
  name: 'li',
  age: 10,
  grade: 60
}
```

给类型取一个含义更明确的名字

需要明确起一个别名不会声明一个新的类型

interface(接口)是会声明一个新的类型的

1. 字面量类型

```
type Weekdays = 'Mon' | 'Tue' | 'Wed' | 'Thu' | 'Fri';
```

字面量类型可以指定变量必须是固定值或者其中的某个(类型的种类只能是基本类型中的)

实际应用中可以搭配联合类型(类型且, 类型或), 类型别名一起使用

1. this的类型