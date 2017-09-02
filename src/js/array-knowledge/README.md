# Array-String
Javascript数组去重:http://www.tuicool.com/articles/uQ7ZjiY  
https://segmentfault.com/a/1190000000513057    


数组赋值：  
var data=[];  
data = data.push(obj);   
这样可以赋值  

const data = ['name','damage','haha','wuyu'];
data.map((key,index)=>{
  return key+index;
});
## js数据类型
基本数据类型: Undefined. Null. Number. String. Boolean.    
复杂数据类型: Object.  

typeof 操作符的返回值类型: String 字符串.  typeof typeof [1,2]  "string"   

"number" -- 如果这个值是数值;  
"string" -- 如果这个值是字符串;  
"boolean" -- 如果这个值是布尔值;  
"undefined" -- 如果这个值未定义;  
"object" -- 如果这个值是对象(包括数组)或者null;  
"function" -- 如果这个值是函数;  

js的几种数据类型：JavaScript数据类型分成两大类  原始数据类型和对象类型；  
原始数据类型：数字 Number,字符串 String, 布尔 Boolean;   
对象数据类型：对象 object；  
特殊数据类型：Undefined. Null  

特殊的原始值：null和undefined；他们不是数字，字符串 和boolean；他们通常代表各自特殊类型的唯一成员

null属于object类型。typeof(null)  
NaN属于number数据类型；typeof(NaN)  
undefined属于undefined数据类型；typeof(undefined)  

未定义的值和定义未赋值的为undefined，null是一种特殊的object,NaN是一种特殊的number。  
（1）undefined与null是相等；（2）NaN与任何值都不相等，与自己也不相等。

http://jingyan.baidu.com/article/64d05a02640111de55f73bbb.html  
http://www.jb51.net/article/35404.htm  
http://www.cnblogs.com/yansj1997/p/4178835.html  

1.JS中typeof与instanceof的区别:  
JavaScript 中 typeof 和 instanceof 常用来判断一个变量是否为空，或者是什么类型的。但它们之间还是有区别的：   

-- typeof 是一个一元运算，放在一个运算数之前，运算数可以是任意类型,它返回值是一个字符串。  
我们可以使用 typeof 来获取一个变量是否存在，如 if(typeof a!="undefined"){alert("ok")}，而不要去使用 if(a) 因为如果 a 不存在（未声明）则会出错，  
对于 Array,Null 等特殊对象使用 typeof 一律返回 object，这正是 typeof 的局限性。

var s="rrrrrr";
var arr=new Array();
if(typeof(s)!="undefined"){
    console.log(typeof(s));
}
if(typeof(s)=="string"){//判断是否是string类型应该这样写
    console.log(typeof(s));
}
if(typeof(arr)=="object"){
  console.log(typeof(arr));
}
http://blog.sina.com.cn/s/blog_532751d90100iv1r.html

var param1 = "string";  
var param2 = new Object();  
var param3 = 10;  
alert(typeof(param1)+"\n"+typeof(param2)+"\n"+typeof(param3));  

document.write ("typeof(1): "+typeof(1));  
document.write ("typeof(NaN): "+typeof(NaN));  
document.write ("typeof(Number.MIN_VALUE): "+typeof(Number.MIN_VALUE));  
document.write ("typeof(Infinity): "+typeof(Infinity));  
document.write ("typeof(\"123\"): "+typeof("123"));  
document.write ("typeof(true): "+typeof(true));  
document.write ("typeof(window): "+typeof(window));  
document.write ("typeof(Array()): "+typeof(new Array()));  
document.write ("typeof(function(){}): "+typeof(function(){}));  
document.write ("typeof(document): "+typeof(document));   
document.write ("typeof(null): "+typeof(null));  
document.write ("typeof(eval): "+typeof(eval));  
document.write ("typeof(Date): "+typeof(Date));    
document.write ("typeof(sss): "+typeof(sss));  
document.write ("typeof(undefined): "+typeof(undefined))  

-- a instanceof b ?alert("true"):alert("false"); //a是b的实例？真:假  
instanceof 用于判断一个变量是否某个对象的实例，如
var a=new Array();
alert(a instanceof Array); 会返回 true，同时 alert(a instanceof Object) 也会返回 true;这是因为 Array 是 object 的子类。  
再如：function test(){};var a=new test();alert(a instanceof test) 会返回true
谈到 instanceof 我们要多插入一个问题，就是 function 的 arguments，我们大家也许都认为 arguments 是一个 Array，但如果使用 instaceof 去测试会发现 arguments 不是一个 Array 对象，尽管看起来很像。
另外：测试 var a=new Array();if (a instanceof Object) alert('Y');else alert('N');
得'Y’
但 if (window instanceof Object) alert('Y');else alert('N');
得'N'  
所以，这里的 instanceof 测试的 object 是指 js 语法中的 object，不是指 dom 模型对象。  
使用 typeof 会有些区别
alert(typeof(window)) 会得 object  


## delete它既删除其值,也删除其位置   
const data = ['name','damage','haha','wuyu'];  
const data = [0: 'name',1:'damage',2: 'haha',3: 'wuyu'];   
delete data[0];    
console.log(data);   // 返回值  [1:'damage',2: 'haha',3: 'wuyu'];   
console.log(data.length);  // 返回值4  

for (key in data) {
	console.log(key);  
	console.log(data[key]);  
}

## splice删除之后会重新排序
const data = ['name','damage','haha','wuyu'];  
const data = [0: 'name',1:'damage',2: 'haha',3: 'wuyu'];  
data.splice(0, 1);  
console.log(data);  
console.log(data.length);  // 返回值3  

小结  
[delete 操作符用来删除一个对象的属性。](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/delete)  
语法  
delete expression  
 expression 应该是一个对象的属性引用，例如：  
delete object.property   
delete object['property']  
eg:  
const data = {name:'zhangsan',age:23};  
delete data.name;  
console.log(data);  
如果 expression 的计算结果不是一个对象的属性引用，那么，delete不会起任何作用。  

splice常用于操作数组里的值  

# 数组concat() and push() and  unshift()
concat()方法操作后返回一个新的数组，原来的数组没有变化；    
push()是在数组的末尾插入一条数据，操作之后修改了原来的数组；  
unshift()是在数组的第一行插入一条数据，操作之后修改了原来的数组；  
