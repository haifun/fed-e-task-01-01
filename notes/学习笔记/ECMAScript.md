ECMAScript 2015

#### 1.let和块级作用域 

```
{
  let a = 10;
  var b = 1;
}

a // ReferenceError: a is not defined.
b // 1
```

**不存在变量提升**


#### 2.const 设置常量

设置必须要赋值，复制后不能修改值（引用的除外）

如：
```
const num = '1'

num = 2; //VM821:1 Uncaught TypeError: Assignment to constant variable.
```

```
const obj = {};
obj.name = 'foo';
console.log(obj.name);// "foo"

```

#### 3.数组解构

```

let [foo, bar, baz] = [1, 2, 3];

foo //1
bar //2
baz //3


let [, , third] = ['foo', 'bar', 'baz'];

third // baz

let [head, ...tail] = [1,2,3,4];
head // 1
tail // [2,3,4]


```

#### 4.对象解构

```
const obj = { name:'foo', age:18 };

const { name } = obj;
console.log(name)


const { name: objName } = obj;
console.log(objName);


const { name: objName = 'jack' } = obj
console.log(objName)
```





模板字符串

带标签的模板字符串

ES2015字符串的扩展方法

ES2015参数默认值

ES2015剩余参数

ES2015 展开数组

ES2015箭头函数

ES2015箭头函数与this

ES2015对象字面量的增强

Object.assign

ES2015 Object.is

ES2015 Proxy

ES2015 Proxy对比defineProperty

ES2015 Reflect

ES2015 Promise

ES2015 class 类

ES2015 静态方法

类的继承

Set

Map

Symbol

Symbol  补充

for ... of循环

可迭代接口

实现可迭代接口

迭代器模式

生成器

生成器应用

ES Modules

ES2016

ES2017











