# this
### 关键字
被调用、作用域
### demo
```
var o = {
  f : function(){ 
    return this.a + this.b; 
  }
};
var p = Object.create(o);
p.a = 1;
p.b = 4;

console.log(p.f()); // 5
```
### apply,call
调用该方法时，会执行函数，并将作用域绑定到指定对象上

```
function add(c, d){
  return this.a + this.b + c + d;
}

var o = {a:1, b:3};

// The first parameter is the object to use as 'this', subsequent parameters are passed as 
// arguments in the function call
add.call(o, 5, 7); // 1 + 3 + 5 + 7 = 16

// The first parameter is the object to use as 'this', the second is an array whose
// members are used as the arguments in the function call
add.apply(o, [10, 20]); // 1 + 3 + 10 + 20 = 34
```
### bind
调用该方法，会生成一个相同函数体和作用域的函数。无论如何执行对应的函数，作用域都指向bind的作用域



