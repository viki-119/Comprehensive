################################################################################################

escape():转换成计算机通用的Unicode码  
unescape():解码  
isFinite():判断一个数是否是有限的  
isNaN():判断一个变量是否为“非数字”  
parseFloat():把字符串前缀的数字转换成浮点型  
parseInt():把字符串前缀的数字转换成整型  
eval(): 执行一段js代码  

################################################################################################

escape():
010101.....>a,b,c,1,2,
字符集的概念：字符集就是编码...>字符的映射
例：65..>A,   97....>a,   01000001...>65

Ascii 字符集
[00000000]--------[11111111]--->0-255,-128- +127

西欧字符集
128-255也利用起来，表示

来到中国
[00000000]汉字，最多也不过256个
常用数字3000多，全部3W+
[00000000][00000000]------[11111111][11111111]
0----->65535之间，
用2个字节表示一个汉字：gb2312（只存7000左右汉字 少）  

gbk---(汉字+日文+棒文)
32456---gbk--->国
32456---jis--->淄
存在问题

Unicode编码集
Unicode规定“国”在Unicode有一个独特的号，假设是29876，
Unicode编码集给世界上大部分的语言每个字符集都分配了一个号码
国[gbk]----->unicode[29876]----> 日本--->从unicode得到国字
把字符转换成Unicode对应的编码，以适应不同的计算机平台传输；
转换用escape() 和unescape();
var str="人民币";
alert(escape(str));




################################################################################################

parseInt():把字符串的前缀 部分的数字分析成整型数字；  
var str="12.987asdfasd";
parseInt(str);
如果前缀部分不是数字，分析出“非数字”----NaN
如果遇到前缀部分有小数的情况，舍弃小数点后面的部分，保留整数部分；
parseFloat：把字符串的   前缀 部分的数字分析成浮点型；


################################################################################################

NaN--->一个特殊变量，代表非数字；
isNaN() 用来判断某个变量为“非数字”，NaN  
//isNaN():使用这个函数的典型情况是检查 parseInt 和 parseFloat 方法的返回值
一般判断是数字用     if(!isNaN(param)){   }

1/0 ;   -1/0
isFinite()
返回一个 Boolean 值,指明所提供的数字是否是有限的。
isFinite(number)
必选项 number 参数为任意的数值。
说明
如果 number 不是 NaN 、负无穷或正无穷，那么 isFinite 方法将返回 true 。 如果是这三种情况，函数返回 false 。



################################################################################################

eval()  用来执行一段js代码；
/*************************************************************************_/
var t=3;
t+=3;
eval('t+=3');
alert(t);
/**_***********************************************************************/
eval('alert("asdfalksdjf")');

################################################################################################

window.scroll(x,y)跳转到页面的指定坐标点，目标点是以像素为单位从页面左上角为标记点的距离，水平和垂直滚动条滚动到相应x,y点

document.getElementById('but').onclick=function(){
    var cha=(document.body.scrollHeight-document.body.clientHeight)/2;
    scroll(0,cha.toFixed(0));
}



################################################################################################
Js内置对象部分

一、在js中，除undefined外，其他一切数据  /  所有的变量都可以被js引擎包装成对象来处理；
比如 str="abcd";//字符串本身没有length属性，但在你调用str.length
在前一瞬间，js引擎把str包装成对象；

1.------string对象
字符串对象的方法：
str.charAt(index) 寻找字符串中指定位置的一个字符
str.concat(string),连接两个或更多个字符串；
str.indexOf(string)返回出现字符串的位置；
str.substr(num1,[num2])截取字符串；
http://my.oschina.net/u/1434139/blog/224271
str.toLowerCase()换成小写；
str.toUpperCase()换成大写；
str.replace(str1,str2)字符串替换；

截取所需要的字符长度
var ss="它返回值是一个字符串，该字符串说明运算数的类型。typeof 一般只能返回如下几个结果：";
if(ss.length>10){
var tt=ss.substr(0,10)
document.write(tt+"...")
}

对于字符串，布尔型，数值型，数组，null；
这些变量，虽然没有属性，但在调用的前一瞬间，js会为他们包装成对象并赋予一些属性和方法；

二、js内置对象:
Date、Math、Number、Boolean、String、Array、RegExp、Function
1.  日期时间对象类  Date();   必须通过new获得对象;
   //Date()函数是所有日期时间对象的一个“抽象模板”,
   它是一个内置对象——而不是其它对象的属性,允许用户执行各种使用日期和时间的过程。
   　方法
   　　getDate() 查看Date对象并返回日期
   　　getDay() 返回星期几
   　　getHours() 返回小时数
   　　getMinutes() 返回分钟数
   　　getMonth() 返回月份值
   　　getSeconds() 返回秒数
   　　getTime() 返回完整的时间
   　　getTimezoneOffset() 返回时区偏差值(格林威治平均时间与运行脚本的计算机所处时区设置之间相差的分钟数)
   　　getYear() 返回年份
   　　parse() 返回在Date字符串中自从1970年1月1日00:00:00以来的毫秒数(Date对象按照毫秒数的形式存储从那时起的日期和时间)但是注意,该方法当前不能正确运行
   　　setDate() 改变Date对象的日期
   　　setHours() 改变小时数
   　　setMinutes() 改变分钟数
   　　setMonth() 改变月份
   　　setSeconds() 改变秒数
   　　setTime() 改变完整的时间
   　　setYear() 改变年份
   　　toGMTString() 把Date对象的日期(一个数值)转变成一个GMT时间字符串,返回类似下面的值:Weds,15 June l997 14:02:02 GMT(精确的格式依赖于计算机上所运行的操作系统而变)
   　　toLocaleString() 把Date对象的日期(一个数值)转变成一个字符串,使用所在计算机上配置使用的特定日期格式
   　　UTC() 使用Date UTC(年、月、日、时、分、秒),以自从1970年1月1日00:00:00(其中时、分、秒是可选的)以来的毫秒数的形式返回日期
2.  Math;     Math是系统创建好的对象，（和字符串一样）不需要就new就可以直接调用它的属性和方法;
   该对象不是其它对象的一个属性,而是一个内置对象,包含了许多数学常量和函数。
   　　属性
   　　E 欧拉常量,自然对数的底(约等于2.718)
   　　LN2 2的自然对数(约等于0.693)
   　　LN10 10的自然对数(约等于2.302)
   　　LOG2E 以2为底的e的对数(约等于1.442)
   　　LOG10E 以10为底的e的对数(约等于o.434)
   　　PI ∏的值(约等于3.14159)
   　　SQRT1_2 0.5的平方根(即l除以2的平方根,约等于o.707)
   　　SQRT2 2的平方根(约等于1.414)
   　　方法
   　　abs() 返回某数的绝对值(即该数与o的距离,例如,2与一2的绝对值都是2)
   　　acos() 返回某数的反余弦值(以弧度为单位)
   　　asin() 返回某数的反正弦值(以弧度为单位)
   　　atan() 返回某数的反正切值(以弧度为单位)
   　　ceil() 返回与某数相等,或大于该数的最小整数(ceil(-22.22)返回-22;ceil22,22)返回23;ceil(22)返回22)
   　　cos() 返回某数(以弧度为单位)的余弦值
   　　exp() 返回en
   　　floor() 与ceil相反(floor(一22.22)返回一23;floor(22.22)返回22; floor(22)返回22)
   　　log() 返回某数的自然对数(以e为底)
   　　max() 返回两数间的较大值
   　　min() 返回两数间的较小值
   　　pow() 返回m的n次方(其中,m为底,n为指数)
   　　random() 返回0和1之间的一个伪随机数(该方法仅在Netscape
   　　Navigator的UNIX版本中有效)
   　　round() 返回某数四舍五入之后的整数
   　　sin() 返回某数(以弧度为单位)的正弦值
   　　sqrt() 返回某数的平方根
   　　tan() 返回某数的正切值

*根据Math.random方法，random默认返回(0,1)之间的随机，改进函数，接收两个参数，small,big;返回(small,big)之间的随机;

<pre>function random(small,big){
    return (big-small)*Math.random()+small;
}</pre>


!isNaN(parseFloat("123"))    可以判断123是数字

三、Math.round(num) 与 NumberObject.toFixed(index)  的比较
1.Math.round(num) 返回某数四舍五入之后的整数部分;
   而 NumberObject.toFixed(index) 返回的是指定小数位数的数字；

```
function tt(){
  var a=10.555;
  console.log(a.toFixed(2));
}
tt();

function ss(){
  var b=-10.6;
  console.log(Math.round(b));
}
ss();
```

http://baike.baidu.com/subview/9966090/10106910.htm

http://www.zybang.com/question/db9187db4690ae1fe56637b45ed3cec6.html?fr=iks&word=math.round&ie=gbk
