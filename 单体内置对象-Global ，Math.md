# 单体内置对象-Global ，Math

## Global 对象  

* URI编码方法 

* eval()方法

类似ECMAScript解析器

* window 

## Math对象  

* min()和max()

```javascript
var max = Math.max(3, 54, 32, 16);
alert(max); //54
var min = Math.min(3, 54, 32, 16);
alert(min); //3
```

或者
```javascript
var values = [1, 2, 3, 4, 5, 6, 7, 8];
var max = Math.max.apply(Math, values);
```
  
* 舍入方法   

Math.ceil()//向上舍入

Math.floor()//向下舍入

Math.round()//四舍五入  

* 随机数   

random()
