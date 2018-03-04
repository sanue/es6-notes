# 一、Iterator（遍历器）的概念 #
含义：它是一种接口，为各种不同的数据结构提供统一的访问机制。

**任何数据结构只要部署 Iterator 接口，就可以完成遍历操作**

JavaScript 原有的表示“集合”的数据结构，主要是<font color='blue'>**数组（Array）**</font>和<font color='blue'>**对象（Object）**</font>ES6 又添加了 <font color='blue'>**Map和Set**</font>。



## 调用Iterator的场合： ##

- 解构赋值

**demo**:

    let set = new Set().add('a').add('b').add('c');
    
    let [x,y] = set;
    // x='a'; y='b'
    
    let [first, ...rest] = set;
    // first='a'; rest=['b','c'];


- 扩展运算符

**demo**:

    // 例一
    var str = 'hello';
    [...str] //  ['h','e','l','l','o']
    
    // 例二
    let arr = ['b', 'c'];
    ['a', ...arr, 'd']
    // ['a', 'b', 'c', 'd']

- yield*

**demo**:

    let generator = function* () {
      yield 1;
      yield* [2,3,4];
      yield 5;
    };
    
    var iterator = generator();
    
    iterator.next() // { value: 1, done: false }
    iterator.next() // { value: 2, done: false }
    iterator.next() // { value: 3, done: false }
    iterator.next() // { value: 4, done: false }
    iterator.next() // { value: 5, done: false }
    iterator.next() // { value: undefined, done: true }

- 其他场合

.

    for...of
    Array.from()
    Map(), Set(), WeakMap(), WeakSet()（比如new Map([['a',1],['b',2]])）
    Promise.all()
    Promise.race()