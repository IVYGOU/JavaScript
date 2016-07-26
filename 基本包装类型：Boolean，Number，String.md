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
