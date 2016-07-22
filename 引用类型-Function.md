# 引用类型
## Function类型
**函数是对象，函数名是指针**
### 定义
1.函数声明定义
```javascript
function sum1(num1, num2) {
  return num1 + num2;
}
```
2.函数表达式定义
```javascript
var sum2 =function(num1,num2){
return num1+num2;
};
```
NOTE：函数末尾有一个分号
3.函数声明与函数表达式区别
解析器会率先读取函数声明（函数声明提升function  declaration hoisting），使其在执行任何代码之前可用。   
如下使用正确：
```javascript
alert(sum(10, 10));
function sum(num1, num2) {
  return num1 + num2;//20
}
```
若此处使用函数表达式：
```javascript
alert(sum(10, 10));
var sum = function(num1, num2) {
  return num1 + num2;//出错，Uncaught TypeError: sum is not a function
};
```

### 没有重载
声明两个同名函数的结果是后一个覆盖前一个
```javascript
function sum(num1, num2) {
  return num1 + num2;
}
var sum = function(num1) {
  return num1 + 10;
};
console.log(sum(10, 100));//20，多余的参数会被忽略
```

### 作为值的函数
函数可作为参数传递给另一个函数，也可作为另一个函数的返回值。     

1.作为参数
```javascript
function callSomeFunction(someFunction, someArgument) {
  return someFunction(someArgument);
}
function add10(num) {
  return num + 10;
}
var result = callSomeFunction(add10, 10);
console.log(result);//20
```
NOTE：此处传递的参数是函数指针，必须去掉函数后面的圆括号。  （访问函数的指针而不执行的时候）    


2.作为返回值
```javascript
function createComparisonFunction(propertyName)
{
  return function(object1, object2) 
  {
    var value1 = object1[propertyName];
    var value2 = object2[propertyName];//使用方括号表示法来取得给定属性的值
    if (value1 < value2) 
    {
      return -1;
    } else if (value1 > value2) 
    {
      return 1;
    } else(value1 = value2) 
    {
      return 0;
    }
  };
}
var data=[{name:"Mike",age:21},{name:"Ivy",age:25}];
data.sort(createComparisonFunction("name"));
console.log(data[0].name);//Ivy
data.sort(createComparisonFunction("age"));
console.log(data[0].name);//Mike
```



