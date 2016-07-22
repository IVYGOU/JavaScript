# 引用类型

## Object 类型
```javascript
var person = new Object();
person.name = "IVY";
person.age = 29;
```
## Array 类型
```javascript
var person = new Array( );
```
或
```javascript
var person = new Array(20);//Array的length为20,length不是只读的，可以通过其属性在数组末尾增加或删除项
```
或
```javascript
var person = new Array("blue","red","green");//Array包含3个字符串数组
```
或可以省略new操作符

### 检测数组
```javascript
if (value instanceof Array) { }
```
或
```javascript
if (Array.isArray(value)) { }
```

### 转换方法

1.toString()方法，valueOf()方法
```javascript
var colors = ["red", "blue", "green"];
alert(colors.toString());//toString()返回字符串拼接，以逗号分隔的字符串    red，blue，green
alert(colors);//alert会在后台调用toString()方法，等价于上面做法red，blue，green

alert(colors.valueOf());//valueOf()返回数组    red，blue，green
```
2.toLocaleString()方法
```javascript
alert(colors.toLocaleString());/调用数组每一项的toLocaleString()方法
```
### 栈方法
**LIFO(后进先出)**

push() 向数组末端添加项  

pop() 数组末尾移除最后一项，数组长度减1
```javascript
var colors = new Array();
var count = colors.push("red", "green"); //推入两项
alert(count);//2

count = colors.push("green");//推入另一项
alert(count);//3

var item = colors.pop();//取得最后一项
alert(item);//green 
alert(colors.length);//2
```
### 队列方法
**FIFO(后进先出)**

shift() 移除数组第一个项并返回该项，数组长度减1    

unshift() 数组前端添加任意个项并返回新数组长度
```javascript
var colors = new Array();
var count = colors.push("red", "green"); //推入两项
alert(count);//2
count = colors.push("green");//推入另一项
alert(count);//3

var item = colors.shift();//取得第一项
alert(item);//red 
alert(colors.length);//2

var count = colors.unshift("brown");
alert(count); //3
```
### 重排序

reverse()反转数组项
```javascript
var values = [1, 2, 3, 4, 5];
alert(values.reverse());//5,4,3,2,1
```
sort()  调用toString()方法，比较所得字符串进行升序排列
```javascript
var values = [0, 1, 5, 10, 15];
alert(values.sort()); //0,1,10,15,5,首先比较数组第一项的大小，排序不是最佳方案
```
sort()排序改良【v8源码中sort()具体实现为改良版快速排序】
```javascript
function compare(value1, value2) {
  if (value1 < value2) {
    return -1;
  } else if (value1 > value2) {
    return 1;
  } else {
    return 0;
  }
}
var values = [0, 1, 5, 10, 15];
alert(values.sort(compare));//0,1,5,10,15
```
### 操作方法
concat() 基于当前数组中的所有项创建一个新数组。不影响原数组。
```javascript
var colors = ["red", "blue", "green"];
var colors2 = colors.concat("yellow", ["black", "brown"]);
console.log(colors); //["red", "blue", "green"]
console.log(colors2); //["red", "blue", "green", "yellow", "black", "brown"]
```
slice() 基于当前数组中的一个或多个项创建一个新数组。不影响原数组。
```javascript
var colors = ["red", "blue", "green","yellow","black"];
var colors2 = colors.slice(1);//从位置1开始到结束，["blue", "green", "yellow", "black"]
var colors3 = colors.slice(1,3);//从位置1开始到位置2，["blue", "green"]
console.log(colors);
console.log(colors2);
console.log(colors3);
```
**NOTE：slice()中参数若为负数，则用数组长度加上该数来确定相应位置。**

splice() 向数组的中部插入项，改变原数组     

1.删除，2个参数，要删除的第一项的位置和删除的项数
```javascript
var colors = ["red", "blue", "green","yellow","black"];
var removed = colors.splice(0,1);//删除第一项
console.log(colors);//["blue", "green", "yellow", "black"]，原数组被删除第一项
console.log(removed);//["red"]，被删除的项
```
2.插入，3个参数，起始位置，要删除的项数，要插入的项
```javascript
var colors = ["red", "blue", "green","yellow","black"];
var removed = colors.splice(1,0,"orange");//从位置1开始插入两项
console.log(colors);//["red", "orange", "blue", "green", "yellow", "black"]
console.log(removed);//[]，未删除因此返回空数组
```

3.替换，3个参数，起始位置，要删除的项数，要插入的项
```javascript
var colors = ["blue", "green", "yellow", "black"];
var removed = colors.splice(1, 1, "red", "purple");//插入两项，删除一项
console.log(colors);//["blue", "red", "purple", "yellow", "black"]
console.log(removed);//["green"]
```
### 位置方法
indexOf() 从数组开头向后寻找，未找到返回-1。
2个参数，要查找的字符串，查找的开始位置（未指定则默认为初始位置）
```javascript
var numbers = [1, 2, 4, 5, 8, 2, 1, 4, 0];
console.log(numbers.indexOf(4)); //2，它会找到数字4第一次出现的位置
console.log(numbers.indexOf(4,4)); //7
```
lastIndexOf() 从数组末尾向前寻找，未找到返回-1
```javascript
var numbers = [1, 2, 4, 5, 8, 2, 1, 4, 0];
console.log(numbers.lastIndexOf(4));//7
console.log(numbers.lastIndexOf(4,4)); //2
```
### 迭代方法
对数组中的每一项运行给定函数，每一项运行的函数包括3个参数：数组项的值，数组项所在位置，数组本身   

every() 函数对每一项都返回true，则返回true   

some() 函数中有一项都返回true，则返回true
```javascript
var numbers = [1, 2, 4, 5, 8, 2, 1, 4, 0];
var everyResult = numbers.every(function(item, index, array) {
  return (item > 2);
});
var someResult = numbers.some(function(item, index, array) {
  return (item > 2);
});
console.log(everyResult); //false
console.log(someResult); //true
```
filter() 是否在返回的数组中包含某一项
```javascript
var numbers = [1, 2, 4, 5, 8, 2, 1, 4, 0];
var filterResult = numbers.filter(function(item, index, array) {
  return (item > 2);
});
console.log(filterResult);// 4,5,8,4
```
forEach() 没有返回值，本质上与使用for循环迭代数组一样
```javascript
var numbers = [1, 2, 4, 5, 8, 2, 1, 4, 0];
numbers.forEach(function(item, index, array) {
 //执行某些操作
});
```
map()
```javascript
var numbers = [1, 2, 4, 5, 8, 2, 1, 4, 0];
var mapResult = numbers.map(function(item, index, array) {
  return item * 2;
});
console.log(mapResult);//[2, 4, 8, 10, 16, 4, 2, 8, 0]
```

### 缩小方法
reduce()   

reduceRight()
```javascript
var numbers = [1, 2, 4, 5, 8, 2, 1, 4, 0];
var sum = numbers.reduce(function(prev, cur, index, array) {
  return prev + cur;
});
console.log(sum);//27
```
