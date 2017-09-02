################################################################################################

window对象的子对象
<pre>window.navigator :表示浏览器的相关信息；
    navigator对象的属性
             appCodeName：浏览器的代码名(例如,Mozilla)；
             appName ：浏览器名称；
             appVersion:浏览器版本；
             userAgent：用户代理信息；、//由客户机送到服务器的用户与代理头标文本
             cookieEnabled:是否支持cookie；
             platform：返回运行浏览器的操作系统平台。(不好用)
             cpuClass：获取平台cpu（兼容性差）
       用法：window.navigator.appName            或者  navigator.appName

window.history:历史记录或者控制前进后退；
     history对象的属性：
             length:   历史记录的条数(指窗口上的历史记录)；
             back:   后退；
             forward：前进；
             go(number);
       用法：history.length；      history.back(-1);    history.forward(1);   
                  history.go(1);history.go(-1);

window.screen:表示分辨率信息；
       screen对象的属性；
              width：
              height：
              availWidth：可用宽分辨率；
              availHeight:可用高分辨率；
         用法：screen.width;

window.location:地址栏，可以控制页面跳转；
         location对象的属性；
               host:  主机
               port：端口
               href ：地址
               pathname：路径
               protocol：协议
               search：查询字符串
               assign(url):页面跳转
         用法：获取当前地址  location.href;     ||   location.href="http://www.baidu.com"

window.document:Dom模型；
</pre>

Bom模型：
浏览器 对象 模型
window对象是最大的对象，所有对象都在其内部；因此写document默认就是在最全局的window对象或子对象；


################################################################################################

暴力添加dom节点---innerHTML→非w3c标准但主流浏览器都支持

这里的innerHTML是dom的属性  
![20150831233609](https://cloud.githubusercontent.com/assets/13939585/9582693/7dfff6d4-5039-11e5-8787-b3ea91d90202.png)
还可以插入一段代码到指定的dom中
![20150831234557](https://cloud.githubusercontent.com/assets/13939585/9582865/82e9699a-503a-11e5-8a85-f3d26f6f103d.png)

直接插入html内容【不是w3c的标准，但是主流浏览器都支持，而且非常好用】

innerHTML 属性
节点的innerHTML属性是可读可写，
读是指把某个节点的内部的html代码读取出来；
如果赋值，则相当于把节点的html代码更新；
