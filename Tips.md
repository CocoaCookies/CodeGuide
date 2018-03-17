# 小技巧

## 三元操作符

简单的 if...else 语句可以使用三元操作符来代替

```
let answer
if (x > 10) {
    answer = 'is greater'
} else {
    answer = 'is lesser'
}
```

简写：

```
const answer = x > 10 ? 'is greater' : 'is lesser'
```

## 短路赋值

为变量赋值时，如果害怕赋值成 null，undefined 或空值，可以使用短路赋值

```
if (variable1 !== null || variable1 !== undefined || variable1 !== '') {
     let variable2 = variable1
}
```

简写：

```
const variable2 = variable1 || 'new'
```

## 十进制指数

当需要写数字带有很多零时（如 10000000），可以采用指数（1e7）来代替

```
1e7 === 10000000 // true
```

## 对象属性简写

如果属性名与 key 名相同，则可以采用 ES6 的方法：

```
const obj = { x:x, y:y }
```

简写：

```
const obj = { x, y }
```

## 箭头函数

```
function sayHello(name) {
  console.log('Hello', name)
}

setTimeout(function() {
  console.log('Loaded')
}, 2000)

list.forEach(function(item) {
  console.log(item)
})

const func = function func() {
  return { foo: 1 }
}
```

简写:

```
sayHello = name => console.log('Hello', name)

setTimeout(() => console.log('Loaded'), 2000)

list.forEach(item => console.log(item))

const func = () => ({ foo: 1 })
```

箭头函数有几个使用注意点。

1.  函数体内的 this 对象，就是定义时所在的对象，而不是使用时所在的对象。

2.  不可以当作构造函数，也就是说，不可以使用 new 命令，否则会抛出一个错误。

3.  不可以使用 arguments 对象，该对象在函数体内不存在。如果要用，可以用 rest 参数代替。

4.  不可以使用 yield 命令，因此箭头函数不能用作 Generator 函数。

## 参数默认值

```
function volume(l, w, h) {
  if (w === undefined)
    w = 3
  if (h === undefined)
    h = 4
  return l * w * h
}
```

简写：

```
volume = (l, w = 3, h = 4 ) => (l * w * h)

volume(2) //output: 24
```

## 模板字符串

```
const db = 'http://' + host + ':' + port + '/' + database
```

简写：

```
const db = `http://${host}:${port}/${database}`
```

## 解构赋值

```
let [foo, [[bar], baz]] = [1, [[2], 3]]
foo // 1
bar // 2
baz // 3

let [ , , third] = ["foo", "bar", "baz"]
third // "baz"

let [x, , y] = [1, 2, 3]
x // 1
y // 3

let [head, ...tail] = [1, 2, 3, 4]
head // 1
tail // [2, 3, 4]

let [x, y, ...z] = ['a']
x // "a"
y // undefined
z // []
```

[详细介绍](http://es6.ruanyifeng.com/#docs/destructuring)

##
