* 全局的this
console.log(this.document === document);//true    
console.log(this===window);//true  
this.a = 312;   
console.log(window.a);//312
* 一般函数的this
```js
  function f1() {
    return this;
  };
  console.log(f1() === window);//函数的this指代全局对象
  function f2() {
    "use strict"; //严格模式下this指代的是undefined
    return this;
  }
  console.log(f2() === undefined);
```
* 作为对象方法的函数的this(不带参)  
```js
var o={
  prop:37,
  f:function() {
    return this.prop;
  },
}
console.log(o.f());
```
* 作为对象方法的函数的this(带参)
```js
var o={prop:37};
function independent() {
  return this.prop;
}
o.f=independent;
console.log(o.f());
```
* 对象原型链上的this
```js
var o={
  f:function(){
    return this.a + this.b;
  }
}
var p =Object.create(o);
p.a = 1;
p.b = 4;
console.log(p.f());
```
* get/set方法与this
```js
function modulus(){
  return Math.sqrt(this.re*this.re + this.im*this.im);
}
var o={
  re:1,
  im:-1,
  get phase(){
    return Math.atan2(this.im,this.re);
  }
}
Object.defineProperty(o,'modulus',{
  get:modulus,
  enumerable:true,
  configurable:true
});
console.log(o.phase,o.modulus);
```

* 构造器中的this
```js
function MyClsaa(){
  this.a=39;
}
var o=new MyClass();
console.log(o.a);
function C2(){
}
Object.defineProperty(o,'modulus',{
  get:modulus,
  enumerable:true,
  configurable:true
});
console.log(o.phase,o.modulus);
```

* call/apply方法与this
```js
function add(c,d){
  return this.a + this.b + c + d;
}
var o = {
  a:1,
  b:3
};
add.call(o,5,8);
add.apply(o,[10,20]);
function bar(){
  console.log(Object.prototype.toString.call(this));
}
bar.call(7);
```

* bind方法与this
```js
function f(){
  return this.a+1;
}
var g = f.bind({a:"test"});
console.log(g());
var o = {a:37,f:f,g:g};
console.log(o.f(),o.g());//37,test
```
