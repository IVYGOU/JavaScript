# this用法详解
this绑定规则
* 隐式绑定
是否被某个对象拥有或包含   

```javascript
var a = 3;
function foo() {
  console.log(this.a);
}
var obj = {
  a: 2,
  foo: foo
};
obj.foo();//2,foo()函数被用作obj对象的一个方法来调用，this.a等于obj.a
```
NOTE:如果对象属性的引用是多层的，只有最后一层会影响调用位置

* 显式绑定
使用一些方法强制将函数绑定于一个对象上，如call(),apply()    

```javascript
function foo() {
  console.log(this.a);
}
var obj = {
  a: 2,
  foo: foo
};
foo.call(obj);
```

* new绑定   

```javascript
function foo(a) {  
   this.a = a;  
}  
var bar = new foo(2);  
console.log(bar.a);  //2
```
使用new调用函数，发生构造函数调用时，
1.会产生一个新的对象
2.这个对象会被执行[__proto__]的链接(bar.__proto__=Foo.prototype)
3.这个新对象会绑定到函数调用的this上
4.如果函数没有返回其他对象，那么new表达式中的函数调用会自动返回这个新对象   

当使用new操作符执行foo函数时，就创建了一个全新的对象并且赋值给了变量bar。进行原型链接之后foo函数活动对象的this属性被绑定在新创建的对象bar上，foo函数并没有返回值，所以自动返回new创建的bar对象。

* 默认绑定
不符合以上规则的默认绑定,在非严格模式下被绑定在全局对象上

```javascript
function foo() {  
    console.log(this.a);  
}  
var a = 2;  
foo(); //undefined
```
