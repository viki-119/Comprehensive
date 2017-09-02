* 全局的this
console.log(this.document === document);  
console.log(this===window);  
this.a = 312;   
console.log(window.a);
* 一般函数的this
```js
  function f1() {
    return this;
  };
  console.log(f1() === window);
  function f2() {
    "use strict"; //see strict mode
    return this;
  }
  console.log(f2() === undefined);
```
* 作为对象方法的函数的this
```js
var o={
  prop:37,
  f:function() {
    return this.prop;
  }
}
console.log(o.f());
```

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
