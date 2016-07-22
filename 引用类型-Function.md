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
NOTE:函数末尾有一个;
```javascript
alert(sum(10, 10));
function sum(num1, num2) {
  return num1 + num2;
}
```
