function test(){
  alert(333);
}

function test(ttt){
alert(ttt);
}
test();
上面这段代码下面的不管你test()方法里有没有参数，都会调用下面带参的方法，下面的方法直接覆盖了上面的方法。

/*********************************************************************************************/

function test(){
alert("uuuu");
}
function show(callback){
     callback();
}
show(test);//上面这是不传参的调用方法

//下面这是传参的调用方法
function show(callback){
     callback("rrrr");
}
show(function test(ttt){
    alert(ttt)
})


/*********************************************************************************************/
//下面这个函数，可以立即执行
自执行函数
(function run(){
 alert("hhhhh")
})()

//当然还可以传递参数
(function run(uu){
 alert(uu)
})("hhhhh")


/*********************************************************************************************/
function test(){
   var name="xxx";
   console.log(arguments)
}
test(1,2,3)

//简单对象的创建
var name="outName";
var o={
   name:"inName",
   show:function(){
   alert(this.name);
}
}
o.show();


/*********************************************************************************************/
function person(){
this.name ="inName";
}
person.prototype.xx="xx"; //不能同下面混合使用  这样定义是无效的
person.prototype={age:12,sex:"man"}   //这种定义的优先级更高 ；属性使您有能力向对象添加属性和方法
var person=new person();
person.name;
person.age;
person.sex;
Person.xx;//这里访问不到


/*********************************************************************************************/
一直困惑有的&lt;script language="javascript"&gt;这样写 有的这样&lt;script type="text/javascript"&gt;写今天找到了在这里标记一下 ，w3c的标准已经废弃了&lt;script language="javascript"&gt;的写法了改用&lt;script type="text/javascript"&gt;来标记引用外部javascript文件这句话标明引用的外部文件为javascript格式文件

http://gghaomm.iteye.com/blog/984589
