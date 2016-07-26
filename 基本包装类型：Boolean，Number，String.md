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

1， toString()    

```javascript
var num = 10;
alert(num.toString()); //”10”,默认10进制
alert(num.toString(2)); //”1010”，2进制
alert(num.toString(8)); //”12”，8进制
alert(num.toString(10)); //”10”，10进制
alert(num.toString(16)); //”a”，16进制
```
2， toFixed() 按照指定的小数位返回数值的字符串表示

```javascript
var num = 10;
alert(num.toFixed(2)); //”10.00”
```    

```javascript
var num = 10.005;
alert(num.toFixed(2)); //”10.01”
```
3，toExponential() 指数表示法   
 
```javascript
var num = 10;
alert(num.toExponential(1)); //”1.0e+1”
```

4， toPrecision() 会根据要处理的数值决定使用toFixed()或toExponential()

```javascript
var num = 99;
alert(num.toPrecision(1)); //”1e+2”
alert(num.toPrecision(2)); //”99”
alert(num.toPrecision(3)); //”99.0”
```  
* String
 
`var stringObject = new String(“hello world”);`   
 
length属性 

```javascript
var stringValue = "hello world";
alert(stringValue.length); //”11”
```   

1, 字符方法  

charAt() 以单字符字符串的形式返回给定位置的字符   
```javascript
var stringValue = "hello world";
console.log(stringValue.charAt(1)); //e
```       

也可以直接使用：   

```javascript
var stringValue = "hello world";
alert(stringValue[1]);//e
```

charCodeAt() 以单字符字符串的形式返回给定位置的字符编码    

```javascript
var stringValue = "hello world";
console.log(stringValue.charCodeAt(1)); //101
```  

2, 字符串操作方法 

concat() 字符串拼接 
```javascript
var stringValue = "hello ";
var result = stringValue.concat("world", "!");
console.log(result); //”hello world”
console.log(stringValue); //”hello”
```
 3，字符串位置方法 
 
 `indexOf()` and `lastIndexOf()`

```javascript
var stringValue = "hello world";
console.log(stringValue.indexOf("o")); //4
console.log(stringValue.lastIndexOf("o")); //7
```  

4, trim() 删除前缀和后缀的所有空格  
 
 ```javascript
var stringValue = "hello world";
var trimmedStringValue = stringValue.trim();
console.log(stringValue); //” hello world “
console.log(trimmedStringValue); //”hello world” 
```

5,  字符串大小写转换    

toLowerCase(), toLocaleLowerCase(), toUpperCase(), and toLocaleUpperCase().    

 ```javascript
var stringValue = “hello world”;
alert(stringValue.toLocaleUpperCase()); //”HELLO WORLD”
alert(stringValue.toUpperCase()); //”HELLO WORLD”
alert(stringValue.toLocaleLowerCase()); //”hello world”
alert(stringValue.toLowerCase()); //”hello world”
```

toLocaleUpperCase()，toLocaleLowerCase()是针对特定地区的实现，更稳妥。   

6,  字符串模式匹配方法   

match()    接收一个参数，是一个RegExp对象或者一个正则表达式;返回一个数组。 

```javascript
var text = "cat, bat, sat, fat";
var pattern = /.at/;
//same as pattern.exec(text)
var matches = text.match(pattern);
alert(matches.index); //0
alert(matches[0]); //”cat”
alert(pattern.lastIndex); //0
```

search() 接收一个参数，是一个RegExp对象或者一个正则表达式；返回字符串第一个匹配项的索引。

```javascript
var text = "cat, bat, sat, fat";
var pos = text.search(/at/);
alert(pos); //1
```

replace() 替换子字符串，第一个参数是一个RegExp对象或者一个字符串；第二个参数可以是一个字符串或一个函数   
     
```javascript
var text = "cat, bat, sat, fat";
var result = text.replace("at", "ond");
alert(result); //”cond, bat, sat, fat”
result = text.replace(/at/g, "ond");
alert(result); //”cond, bond, sond, fond”
```


7, localeCompare() 比较两个字符串    

比较在字母表中的位置
```javascript
var stringValue = "yellow";
alert(stringValue.localeCompare("brick")); //1 ，字符串参数之前
alert(stringValue.localeCompare("yellow")); //0，等于字符串参数
alert(stringValue.localeCompare("zoo")); //-1，字符串参数之后
```
 
 8, fromCharCode() 接收字符编码再转换成字符串 
 
 ```javascript
alert(String.fromCharCode(104, 101, 108, 108, 111)); //”hello”
```

 
 
