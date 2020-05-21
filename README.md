### 1.请说出下列最终的执行结果，并解释为为什么

```
var a = [];
for(var i = 0; i<10; i++){
	a[i] = function(){
		conole.log(i);
	}
}
a[6]();
```

答案为：10，
因为for循环里var i定义的是一个全局变量, 最后打印的实际是全局变量i

### 2.请说出下列最终的执行结果，并解释为为什么

```
var tmp = 123;
if (true) {
  console.log(tmp);
  let tmp;
}
```
答案：引用错误，let 不存在变量提升

### 3.结合ES6新语法，用最简单的方式找出数组中的最小值？

```
var arr = [12,34,32,89,4]

Math.min(...arr)

```

### 4.请详细说明var， let， const 三种声明变量的方式之间的具体差别？

```
var 存在变量提升；

console.log(a); // undefined
var a = 1

let 定义块级作用域，不存在变量提升
{
	let b = 1;
	var c = 2
}
console.log(b); // b is not defined
console.log(c); // 2


const 设置常量，设置必须要赋值，赋值后不能修改值（引用的除外）

const num = 1;

```

### 5.请说出下列最终的执行结果，并解释为为什么

```
var a = 10;
var obj = {
	a: 20,
	fn(){
		setTimeout(() => {
			console.log(this.a)
		})
	}
}

obj.fn();
```

答案：20， 箭头函数中的this本身指向外部的this

### 6.简述 Symbol 类型的用途？

可以定义全局唯一的一个值；

### 7.说说什么是浅拷贝、什么是深拷贝？

浅拷贝是拷贝对象的引用，源对象修改后，目标对象也会跟着改变；

深拷贝是拷贝对象的本身，源对象修改后，目标对象不会跟着改变

### 8.谈谈你是如何理解JS异步编程的，EventLoop是做什么的，什么是宏任务，什么是微任务？

异步编程不是等待任务完成后去执行下一个任务；耗时的、执行时间长的任务，会放到异步环境中开始并等待执行，等异步任务完成之后，进入到消息队列中，等待同步任务执行完毕之后依次执行异步任务。

EventLoop 是任务调度和执行的监控者，负责监听消息队列和执行栈。

宏任务：

*setTimeout

*setInterval

*setImmediate

*requestAnimationFrame

*I/O操作

微任务：

Promise， process.nextTick


### 9.将下面异步代码使用Promise改进？

```
setTimeout(function () {
  var a = "hello";
  setTimeout(function () {
    var b = "lagou";
    setTimeout(function () {
      var c = "I ❤️ U";
      console.log(a + b + c);
    }, 10);
  }, 10);
}, 10); */
```

```
const promise = new Promise((resolve, reject) => {
  const a = "hello";
  resolve(a);
})
  .then((result) => {
    const b = "lagou";
    return result + b;
  })
  .then((result) => {
    const c = "I ❤️ U";
    console.log(result + c);
  });
```
### 10.请简述TypeScript与JavaScript之间的关系？

TypeScript是JavaScript的一个超集;

TypeScript最终将编译成普通的JavaScript

### 11.请谈谈你所认为的TypeScript优缺点？

有点：
TypeScript是一种强类型的语言，可以试代码更健壮，原生支持ES6,
即使不了解TypeScript,也可以按照正常的JavaScript来编写

缺点：概念繁多（接口，泛型，枚举等），学习成本高


