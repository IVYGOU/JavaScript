## 基本包装类型：Boolean，Number，String
是特殊的引用类型，与引用类型对象的生存期不同。     

使用new创建的引用类型的实例，在执行流离开当前作用域之前一直都存在内存中；   

基本包装类型只存在于代码执行的一瞬间。

```javascript
var s1 = "some text";
s1.color = "red";
alert(s1.color);//undefined
```

* Boolean  

`var booleanObject = new Boolean(true);`

* Number   

`var numberObject = new Number(10);`

1. toString()    

```javascript
var num = 10;
alert(num.toString()); //”10”,默认10进制
alert(num.toString(2)); //”1010”，2进制
alert(num.toString(8)); //”12”，8进制
alert(num.toString(10)); //”10”，10进制
alert(num.toString(16)); //”a”，16进制
```
2. toFixed() 按照指定的小数位返回数值的字符串表示

```javascript
var num = 10;
alert(num.toFixed(2)); //”10.00”
```    

```javascript
var num = 10.005;
alert(num.toFixed(2)); //”10.01”
```
