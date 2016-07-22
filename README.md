# 值传递参数



##  参数：基本类型
```javascriot
function addTen(num) {
  num += 10;
  return num;
}
var count = 20;
var result = addTen(count);
alert(count); //20,没有变化
alert(result); //30
```
result的变化不会影响外部的count变量。

## 参数：对象
```javascript
function setName(obj) {
  obj.name = "IVY";
}
var person = new Object();
setName(person);
alert(person.name);
```
obj和person引用的是同一个对象，会同时改变。

另外，注意对象是按值传递的，以下证明
```javascript
function setName(obj) {
  obj.name = "IVY";
  obj = new Object();
  obj.name = "Greg";
}
var person = new Object();
setName(person);
alert(person.name);//显示的是"IVY"
```
不会因为函数内部重写obj而改变参数的值，重写的obj变量时引用的是局部对象，函数执行完毕会被销毁。



