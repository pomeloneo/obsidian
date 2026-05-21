# React-Hooks

\#React#

## useState

使用状态, 在函数组件中默认是只有状态没有属性的

**注意事项** - 不可以局部更新 看如下代码

```
import React, {useState} from “react”;
import ReactDOM from “react-dom”;

function App() {
  const [user,setUser] = useState({name:'Nick', age: 18})
  const onClick = ()=>{
    setUser({
      name: 'Jack'
    })
  }
  return (
    <div className="App">
      <h1>{user.name}</h1>
      <h2>{user.age}</h2>
      <button onClick={onClick}>Click</button>
    </div>
  );
}
export default App;
```

本意是想只更新`name`字段, 但是导致`age`丢失 可以使用如下代码

```
import React, {useState} from “react”;
import ReactDOM from “react-dom”;

function App() {
  const [user,setUser] = useState({name:'Nick', age: 18})
  const onClick = ()=>{
    setUser(
            ...user,
            name: ‘Jack'
        )
  }
  return (
    <div className="App">
      <h1>{user.name}</h1>
      <h2>{user.age}</h2>
      <button onClick={onClick}>Click</button>
    </div>
  );
}
export default App;
```

- 地址要变(使用新对象) 如果使用下面的写法是不会改变的

```
import React, {useState} from “react”;
import ReactDOM from “react-dom”;

function App() {
  const obj = {
    name:'Nick',
    age: 18
  }
  const [user,setUser] = useState(obj)
  const onClick = ()=>{
    user.name = 'Jack';
    setUser(user)
  }
  return (
    <div className="App">
      <h1>{user.name}</h1>
      <h2>{user.age}</h2>
      <button onClick={onClick}>Click</button>
    </div>
  );
}
export default App;
```

要使用这种写法

```
import React, {useState} from “react”;
import ReactDOM from “react-dom”;

function App() {
  const obj = {
    name:’Nick’,
    age: 18
  }
  const [user,setUser] = useState(obj)
  const onClick = ()=>{

    setUser({
      name:'Jack',
      age: 18
    })
  }
  return (
    <div className="App">
      <h1>{user.name}</h1>
      <h2>{user.age}</h2>
      <button onClick={onClick}>Click</button>
    </div>
  );
}
export default App;
```

- useState接受函数 useState接受的函数返回一个需要初始化的变量, 这样做的好处就是避免了每次重新执行组件函数的时候, 去新生成那个初始化的变量,

因为JS分析代码遇到函数的时候是不会直接进入到函数内部的, 只有执行的时候才进去

```
import React, {useState} from “react”;
import ReactDOM from “react-dom”;

function App() {

  const [user,setUser] = useState(() => {
    return {
      name:'Nick',
      age: 18
    }
  })
  const onClick = ()=>{

    setUser({
      name:'Jack',
      age: 18
    })
  }
  return (
    <div className="App">
      <h1>{user.name}</h1>
      <h2>{user.age}</h2>
      <button onClick={onClick}>Click</button>
    </div>
  );
}


export default App;
```

- setState可以接受一个函数

```
import React, {useState} from “react”;
import ReactDOM from “react-dom”;

function App() {
  const [n, setN] = useState(0)
  const onClick = ()=>{
    // setN(n+1)
    // setN(n+1)
    /**
     * 你会发现 n 不能加 2, 改成下面函数作为参数的模式就可以了
     */
    setN(i=>i+1)
    setN(i=>i+1)
  }
  console.log(n);
  return (
    <div className="App">
      <h1>n: {n}</h1>

      <button onClick={onClick}>+2</button>
    </div>
  );
}

export default App;
```

如果想连续执行setState操作生效的话, 只有通过这种返回一个变量的函数作为setState的参数时才会生效

具体第一种方式不生效的具体原因, useState那篇文章分析过一些原因, 虽然是执行两次setState, 但是只有第二次触发了重新渲染, 只有重新渲染才会生成新的state

如果改变setState的参数为函数的话, 那就每次setState都会重新渲染, 上一次渲染新生成的state作为第二次setState的新的state

个人觉得我会更倾向于setState接受函数作为参数这种方法, 原因是更可控, 更符合直觉

## useReducer

useReducer也是在践行redux的思想, 大体的用法也差不多, 具体可以分一下几步: - 创建initialState - 创建集合所有操作的额reducer函数 - 传给useReducer, 得到读写API - 调用写操作(dispatch)

```
import React, { useState, useReducer } from “react”;
import ReactDOM from “react-dom”;
import { throwError } from "rxjs";

const initialState = {
  n: 0
}
const reducer = (state, action) => {
  if (action.type === 'add') {
    return {
      ...state,
      n: state.n + action.number
    }
  } else if (action.type === 'multi') {
    return {
      ...state,
      n: state.n * 2
    }
  } else {
    return new Error('错误type')
  }
}

function App() {
  const [state, dispatch] = useReducer(reducer, initialState);
  const { n } = state;
  console.log(state.n);
  const onClick = () => {
    dispatch({ type: “add”, number: 1 });
  };
  const onClick2 = () => {
    dispatch({ type: "add", number: 2 });
  };
  const onClick3 = () => {
    dispatch({ type: "multi" });
  };
  return (
    <div className="App">
      <h1>n: {n}</h1>

      <button onClick={onClick}>+1</button>
      <button onClick={onClick2}>+2</button>
      <button onClick={onClick3}>*2</button>
    </div>
  );
}
export default App;
```

看一个使用useReducer实现的简易表单例子

```
import React, { useReducer } from “react”;
import ReactDOM from “react-dom”;

const initFormData = {
  name: "",
  age: 18,
  nationality: "汉族"
};

function reducer(state, action) {
  switch (action.type) {
    case "patch":
      return { ...state, ...action.formData };
    case "reset":
      return initFormData;
    default:
      throw new Error();
  }
}

function App() {
  const [formData, dispatch] = useReducer(reducer, initFormData);
  const onSubmit = () => {};
  // const patch = (key, value)=>{
  //   dispatch({ type: "patch", formData: { [key]: value } })
  // }
  const onReset = () => {
    dispatch({ type: "reset" });
  };
  return (
    <form onSubmit={onSubmit} onReset={onReset}>
      <div>
        <label>
          姓名
          <input
            value={formData.name}
            onChange={e =>
              dispatch({ type: "patch", formData: { name: e.target.value } })
            }
          />
        </label>
      </div>
      <div>
        <label>
          年龄
          <input
            value={formData.age}
            onChange={e =>
              dispatch({ type: "patch", formData: { age: e.target.value } })
            }
          />
        </label>
      </div>
      <div>
        <label>
          民族
          <input
            value={formData.nationality}
            onChange={e =>
              dispatch({
                type: "patch",
                formData: { nationality: e.target.value }
              })
            }
          />
        </label>
      </div>
      <div>
        <button type="submit">提交</button>
        <button type="reset">重置</button>
      </div>
      <hr />
      {JSON.stringify(formData)}
    </form>
  );
}
export default App;
```

## useContext

context就是上下文的意思 简单来理解这个概念 对于全局来说,全局变量就是全局的上下文 对于局部来说, 局部变量就是局部的上下文 useContext使用方式 - 使用`C = createContext(init)`创建上下文 - 使用`<C.provider>`圈定上下文的作用域 - 在作用域的范围内使用`useContext(C)`来使用上下文

```
import React, { createContext, useState, useContext } from “react”;
import ReactDOM from "react-dom";


const C = createContext(null);

function App() {
  console.log("App 执行了");
  const [n, setN] = useState(0);
  return (
    <C.Provider value={{ n, setN }}>
      <div className="App">
        <Parent />
      </div>
    </C.Provider>
  );
}

function Parent() {
  const { n, setN } = useContext(C);
  return (
    <div>
      我是Parent n: {n} <Child />
    </div>
  );
}

function Child() {
  const { n, setN } = useContext(C);
  const onClick = () => {
    setN(i => i + 1);
  };
  return (
    <div>
      我是Child 我得到的 n: {n}
      <button onClick={onClick}>+1</button>
    </div>
  );
}
export default App;
```

这段代码的更新n的机制就是单向数据流, `Child`通知`App`组件更新n 然后,`App`逐级向下通知更新n

## useEffect

useEffect的作用是代替类组件中的三个生命周期钩子函数`componentDidMount`. `componentDidUpdate`, `componentWillUnmount` 用来执行一些有副作用的操作 useEffect接受两个参数, 第一个函数, 第二个是数组 当第二个参数是空数组时, 表示只有首次渲染时执行这个钩子 当第二个参数不为空时, 表示这个钩子的执行依赖于数组中元素的变化(包括首次执行) 当第二个参数不写时, 表示这个钩子函数只要有state的改变就执行(包括首次)

这个钩子的第一个参数函数可以返回一直函数, 用于组件卸载之前调用, 相当于`componentWillUnmount`

看个例子

```
import React, { useState, useEffect } from “react”;
const App = () => {
  const [n, setN] = useState(0);

  useEffect(() => {
    console.log('只有第一次执行');
  }, []);


  useEffect(() => {
    console.log('n变化的时候执行, 包括第一次执行');
  }, [n]);

  useEffect(() => {
    console.log('只要有state状态改变了就执行');
  });
  useEffect(() => {

    return () => {
      console.log('组件即将被卸载');
    }
  });

  return (
    <div id="x" >n: {n}
      <button onClick={() => setN(n + 1)}>+1</button>
    </div>
  );
};
export default App;
```

## useLayoutEffect

这个hook和useEffect存在一些差别 上面说过useEffect相当于替代那三个生命周期钩子函数, 也就说useEffect这个hook是在render渲染页面之后执行的 如果要在useEffect这hook里面执行一些操作dom, 改变dom中的内容的操作, 可能就会出现屏幕闪烁的现象, 因为useEffect的hook被调用时, 页面已经渲染出dom了

```
import React, { useState, useEffect } from “react”;

const App = () => {
  const [value, setValue] = useState(0);

  useEffect(() => {
    const p = document.querySelectorAll('p');
    for (let i = 0; i < p.length; i++) {
      p[i].innerHTML = 100;
    }
  }, [value]);

  return (
    <div id="x">
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
      <p>value: {value}</p>
    </div>
  );
};
export default App;
```

这段代码不好复现这个情况, 感兴趣的可以多些一些复杂的dom结构试试🥶

为了解决这个问题, 就出现useLayoutEffect useLayoutEffect可以理解为在浏览器将React产生的真实dom渲染到页面之前提供了一次改变dom的机会 可以认为这个时机就是在浏览器渲染真实dom之前, react刚刚产生真实dom之后

所以useLayoutEffect的执行时机一定比useEffect早 看下面两个验证的例子

```
import React, {useState, useRef, useLayoutEffect, useEffect} from “react”;

function App() {
  const [n, setN] = useState(0)
  const time = useRef(null)
  const onClick = ()=>{
    setN(i=>i+1)
    time.current = performance.now()
  }
  /**
   * 改成 useEffect 试试
   */
  useLayoutEffect(()=>{
    if(time.current){
      console.log(performance.now() - time.current)
    }
  })
  return (
    <div className="App">
      <h1>n: {n}</h1>
      <button onClick={onClick}>Click</button>
    </div>
  );
}
export default App;
```

```
import React, {useState, useLayoutEffect, useEffect} from “react”;

function App() {
  const [n, setN] = useState(0)
  const onClick = ()=>{
    setN(i=>i+1)
  }
  useEffect(()=>{
    console.log("useEffect")
  })
  /**
   * 改成 useEffect 试试
   */
  useLayoutEffect(()=>{
    console.log("useLayoutEffect")
  })
  return (
    <div className="App">
      <h1>n: {n}</h1>
      <button onClick={onClick}>Click</button>
    </div>
  );
}
export default App;
```

useLayoutEffect这个hook里面最好执行一些关于dom操作或者影响布局的操作 既然使用了React尽量避免直接操作dom 为了用户体验应该优先使用useEffect, 毕竟useLayoutEffect是在真实dom被渲染到页面之前执行, 还是会有一些性能损耗

## useMemo

了解useMemo之前 首先看一下`React.memo`的作用

```
import React from "react”;
function App() {
  const [n, setN] = React.useState({
    number: 0
  });
  const [m, setM] = React.useState({
    number: 0
  });
  const onClick = () => {
    setN({
        ...n,
        number: n.number + 1
      });
    // setM(m + 1);
  };

  return (
    <div className="App">
      <div>
        <p>n.number: {n.number}</p>
        <button onClick={onClick}>update n</button>
      </div>
      <Child data={n}/>
      <MemoChild data={m}/>
    </div>
  );
}

function Child(props) {
  console.log("child 执行了");
  console.log('假设这里有大量代码')
  console.log(props.data);
  return <div>child: {props.data.number}</div>;
}

const MemoChild = React.memo(Child);

export default App;
```

`React.memo`的作用是避免子组件未更新的情况下重复渲染 仅在子组件依赖的props变化时才重新渲染

下面演示一种使用`React.memo`产生的bug情况

```

import React from "react”;
function App() {
  const [n, setN] = React.useState({
    number: 0
  });
  const [m, setM] = React.useState({
    number: 0
  });
  const onClick = () => {
    setN({
        ...n,
        number: n.number + 1
      });
    // setM(m + 1);
  };

  const testOnClick = () => {}
  console.log(‘App执行了’);
  return (
    <div className=“App”>
      <div>
        <p>n.number: {n.number}</p>
        <button onClick={onClick}>update n</button>
      </div>
      <Child data={n} onClick={testOnClick}/>
      <MemoChild data={m} onClick={testOnClick}/>
    </div>
  );
}

function Child(props) {
  console.log("child 执行了");
  console.log('假设这里有大量代码')
  console.log(props.data);
  console.log(props.onClick);
  return <div>child: {props.data.number}</div>;
}

const MemoChild = React.memo(Child);

export default App;
```

上述代码会发现`React.memo`似乎是没有生效, `MemoChild`组件还是重新渲染了 这是因为每次App组件都会重新执行, 所有每次都会产生新的`testOnClick`函数, 所以`MemoChild`组件认为`props`变化了, 所以重新渲染了

由于这种上述这种情况仅仅使用`React.memo`没法满足要求, 这就引出了`useMemo` 使用`useMemo`改进上面情况

```

import React, {useMemo} from “react”;
function App() {
  const [n, setN] = React.useState({
    number: 0
  });
  const [m, setM] = React.useState({
    number: 0
  });
  const onClick = () => {
    setN({
        ...n,
        number: n.number + 1
      });
    // setM(m + 1);
  };
  const testOnClick = useMemo(() => {
    return () => {
      console.log('验证useMemo');
    }
  }, [m])

  console.log('App执行了');
  return (
    <div className="App">
      <div>
        <p>n.number: {n.number}</p>
        <button onClick={onClick}>update n</button>
      </div>
      <Child data={n} onClick={testOnClick}/>
      <MemoChild data={m} onClick={testOnClick}/>
    </div>
  );
}

function Child(props) {
  console.log(“child 执行了”);
  console.log('假设这里有大量代码')
  console.log(props.data);
  console.log(props.onClick);
  return <div>child: {props.data.number}</div>;
}

const MemoChild = React.memo(Child);

export default App;
```

`useMemo`接受两个两个参数, 第一个是一个`() => value`形式的函数, 返回值就作为被记忆化的值, 第二个参数是个数组, 这个数组的作用类似于之前说过的useEffect钩子的第二个参数, 用于收集依赖

如果数组为空, 那么只在首次执行, 也就是首次过后被记忆化的值就固定不会变了

数组中元素值就是记忆化值变化的依赖, 当数组中的元素改变, 那么就重新生成记忆值

如果第二个参数不填, 那么就默认只要有state改变, 就生成新的记忆值

useMemo类似Vue2的computed

如果仅仅需要记忆函数, 那么可以使用`useCallback`

```

import React, {useCallback} from “react”;
function App() {
  const [n, setN] = React.useState({
    number: 0
  });
  const [m, setM] = React.useState({
    number: 0
  });
  const onClick = () => {
    setN({
        ...n,
        number: n.number + 1
      });
    // setM(m + 1);
  };
  const testOnClick = useCallback(() => {
      console.log('验证useCallback')
  }, [m])

  console.log('App执行了');
  return (
    <div className="App">
      <div>
        <p>n.number: {n.number}</p>
        <button onClick={onClick}>update n</button>
      </div>
      <Child data={n} onClick={testOnClick}/>
      <MemoChild data={m} onClick={testOnClick}/>
    </div>
  );
}

function Child(props) {
  console.log("child 执行了");
  console.log('假设这里有大量代码')
  console.log(props.data);
  console.log(props.onClick);
  return <div>child: {props.data.number}</div>;
}

const MemoChild = React.memo(Child);

export default App;
```

`useCallback(x => log(x), [m])` 等价于 `useMemo(() => x => log(x), [m])`

## useRef

`useRef`提供一个在整个组件的生命周期都不会改变的对象

```
import React, {useRef} from “react”;
function App() {
  const count = useRef(0);
  console.log('count', count);
  const onClick = () => {
    count.current += 1;
    console.log(count.current);
  }
  return (
    <div className="App">
      <p>count: {count.current}</p>
      <button onClick={onClick}>update count</button>
    </div>
  );
}

export default App;
```

useRef返回一个对象, 对象的current保存着初始值, 在整个生命周期中, 返回的对象是不会改变的, 但是可以改变对象的current值 为什么不将初始值直接返回, 还要返回一个对象, 对象的current存储初始值呢

因为如果想要实现一个整个生命周期都不会改变的值, 只有引用值才可以做的到, 这个引用值不改, 只改引用值的属性值

**目前为了已经了解了三类更新state的hook** - useState/useReducer 每次都生成新的state - useMemo/useCallback 是否生成新的state依赖于第二个参数的数组内元素是否改变 - useRef 生成的state在整个生命周期不会改变

useRef不会触发页面重新渲染

## forwardRef

`useRef`既可以用来引用普通的对象 也可以用来引用真实的DOM对象, 并且大部分我们都用来引用DOM对象 比如在实现可控组件的时候

看下面的例子

```

import React, {useRef, useEffect} from “react”;
function App() {
  const ref = useRef(null);
  console.log('ref.current', ref.current);
  useEffect(() => {
    console.log('ref.current-useEffect', ref.current);
  }, [])
  return (
    <div className="App" ref={ref}>

    </div>
  );
}

export default App;
```

这说明只有在真实DOM渲染出来之后才能通过useRef拿到dom对象

再看一个例子

```
import React, {useRef, useEffect} from “react”;
function App() {
  const buttonRef = useRef(null);
  console.log(‘buttonRef-App’, buttonRef.current);
  useEffect(() => {
    console.log('buttonRef-useEffect-App', buttonRef.current);
  })
  return (
    <div className="App">
      <Button ref={buttonRef}></Button>
      {/*
      使用RefButton组件就可以传递ref
      */}
      {/* <RefButton ref={buttonRef}>button</RefButton> */}
    </div>
  );
}
function Button(props, ref) {
  console.log('ref-Button', ref.current);
  useEffect(() => {
    console.log('props-useEffect-Button’, props);
    console.log('ref-useEffect-Button', ref.current);
  })
  return (
    <button ref={ref}>
      {props.children}
    </button>
  )
}
const RefButton = React.forwardRef(Button);
export default App;
```

函数式组件不能传递ref, 可以使用forwardRef来转发ref, 通过组件的第二个参数获取到ref

## useImperativeHandle

看一段代码

```
import React, { useRef, useEffect } from “react”;
function App() {
  const buttonRef = useRef(null);
  useEffect(() => {
    console.log(buttonRef.current);
  });
  return (
    <div className="App">
      <Button2 ref={buttonRef}>按钮</Button2>
      <button
        className=“close”
        onClick={() => {
          console.log(buttonRef);
          buttonRef.current.remove();
        }}
      >
        x
      </button>
    </div>
  );
}

const Button2 = React.forwardRef((props, ref) => {
  return <button ref={ref} {...props} />;
});

export default App;
```

另一段代码

```
import React, {
  useRef,
  useState,
  useEffect,
  useImperativeHandle,
  createRef
} from "react";

function App() {
  const buttonRef = useRef(null);
  useEffect(() => {
    console.log(buttonRef.current);
  });
  return (
    <div className="App">
      <Button2 ref={buttonRef}>按钮</Button2>
      <button
        className="close"
        onClick={() => {
          console.log(buttonRef);
          buttonRef.current.x();
        }}
      >
        x
      </button>
    </div>
  );
}

const Button2 = React.forwardRef((props, ref) => {
  // const realButton = useRef(null);
  const realButton = createRef(null);
  // let realButton = useRef(null);
  // const refCallback = (ele) => {
  //   console.log('ele', ele)
  //   realButton.current = ele;
  // }
  console.log('realButton', realButton.current);
  const setRef = useImperativeHandle;
  setRef(ref, () => {
    return {
      x: () => {
        realButton.current.remove();
      },
      realButton: realButton
    };
  });
  return <button ref={realButton} {...props} />;
  // return <button ref={refCallback} {...props} />;
});

export default App;
```

通过这两段代码的可以看出, 其实`useImperativeHandle`提供了一个在ref在转发之前劫持ref操作ref的机会

上面使用了两种创建ref的方法 分析一下两种创建ref区别 ## createRef & useRef

看代码

```
import React, { useRef, createRef, useState } from “react”;

function App() {
  const [renderIndex, setRenderIndex] = useState(1);
  const refFromUseRef = useRef();
  const refFromCreateRef = createRef();
  if (!refFromUseRef.current) {
    refFromUseRef.current = renderIndex;
  }
  if (!refFromCreateRef.current) {
    refFromCreateRef.current = renderIndex;
  }
  return (
    <div className="App">
       最新index: {renderIndex}
      <br />
      第一渲染记录在refFromUseRef.current:
      {refFromUseRef.current}
      <br />
      第一渲染记录在refFromCreateRef.current:
      {refFromCreateRef.current}
      <br />
      <button onClick={() => setRenderIndex(prev => prev + 1)}>
        re-render
      </button>
    </div>
  );
}
export default App;
```

对于createRef来说, 每次App重新render执行, 都会创建一个全新的ref对象

对于useRef来说, 首次创建ref对象之后就不再改变,这一点之前也讲过, 这里在强调一下两种方式的差别

## 自定义hooks

自定义hook很好理解, 但是用处很多, 很好用 其核心思想就是, 将复杂的数据操作单独封装, 最后暴露出外界需要的接口即可 看一个例子

```
import React, { useRef, useState, useEffect } from “react”;
import useList from “./customer-hook”;

function App() {
  const { list, deleteIndex } = useList();
  return (
    <div className=“App”>
      <h1>List</h1>
      {list ? (
        <ol>
          {list.map((item, index) => (
            <li key={item.id}>
              {item.name}
              <button
                onClick={() => {
                  deleteIndex(index);
                }}
              >
                x
              </button>
            </li>
          ))}
        </ol>
      ) : (
        "加载中..."
      )}
    </div>
  );
}
export default App;
```

`customer-hook.js`文件

```
import { useState, useEffect } from “react”;const useList = () => {  const [list, setList] = useState(null);  useEffect(() => {    ajax("/list").then(list => {      setList(list);    });  }, []); // [] 确保只在第一次运行  return {    list: list,    addItem: name => {      setList([...list, { id: Math.random(), name: name }]);    },    deleteIndex: index => {      setList(list.slice(0, index).concat(list.slice(index + 1)));    }  };};export default useList;function ajax() {  return new Promise((resolve, reject) => {    setTimeout(() => {      resolve([        { id: "1", name: "Frank" },        { id: "2", name: "Jack" },        { id: "3", name: "Alice" },        { id: "4", name: "Bob" }      ]);    }, 2000);  });}
```

上面将所有的数据操作封装到自定义hook当中, 最后暴露出添加,删除接口即可, 这对于代码后期的维护, 代码的重构, 增加新功能有很多好处, 原理简单易懂, 用处强大👍, 一定要利用好这个功能

## 总结

所有关于hooks示例代码 [react-theory/src/hooks at master · neo-to/react-theory · GitHub](https://github.com/neo-to/react-theory/tree/master/src/hooks)