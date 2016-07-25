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
obj.foo();
```
