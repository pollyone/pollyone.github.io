[TOC]

### JavaScript概述

- 简介：是基于对象和事件驱动的语言，应用于客户端；是基于对象的，它给我们提供了很多对象，可以直接拿过来使用。
  - 事件驱动：html做网站的静态效果，javasript做出动态效果；
  - 客户端：即浏览器；
- 特点：
  - 交互性（信息的动态交互）
  - 安全性（不可以直接访问本地硬盘）
  - 跨平台性（只要是可以解析js的浏览器都可以执行，和平台无关）
- javascript的组成
  - ECMAScript
    - ECMA：欧洲计算机协会
    - 由ECMA组织指定的js的语法，语句……
  - BOM【broswer  object  model】：浏览器对象模型
  - DOM【document object model】：文档对象模型

### java和javascript的区别

- java是sun公司开发；js是网景公司；
- java是面向对象；javascript是基于对象的；
- java是强类型的语言；js是弱类型的语言；
- java需要先编译成class文件才可以运行；而js只需要解析就可以运行；

### js和html的结合方式

- 方法一：使用一个标签< script type=“text/javascript” >js代码；< /script>

- 方法二： 使用script标签，引入一个外部的js文件
  - 创建一个js文件，写js代码；
  - < script type="text/javascript" src="1.js">< /script >

> 使用第二种方法的时候，不要再script标签里面写js代码了，因为它不会执行

### js的原始类型和声明变量

- java的基本类型：byte,short,int,long,float,double,char,boolean
- js的原始类型：
  - string：字符串，如：var str=“abc”;
  - number：数字类型，如：var m=10;
  - boolean：true和false，如：var flag=true;
  - null：获取对象的引用，null表示对象引用为空；
  - undifined：定义一个变量，没有赋值，如var  aa;

> js定义变量都使用关键字-var；名称可以自定义；

> typeof：查看当前变量的数据类型

### js的语句- 和java里面的差不多

- java里面的语句：if判断；switch语句；for循环，while循环，do-while循环

- js里面的这些语句
  - if判断语句
  - switch语句：js里面支持所有的类型

### js的运算符

和java的不同：

- js中不区分小数和整数，123/1000*1000在js中是123，但是在java中是0；
- Boolean类型可以进行运算，false就是0或者null，非0非空是true，默认用1显示；

```html
<script type="text/javascript">
            alert(false);//false
            alert(true);//true
            alert(false+1);//1
            alert(true+1);//2
        </script>
```

- 字符串的相加和相减
  - 相加做的是字符串的连接运算；
  - 相减做的是数的减法运算，如果字符串不是数字而使用了相减，会出现Nan；

```html
	<script type="text/javascript">
           var i=123;
           alert(i/1000*1000);//123
           var i2="49";
           alert(i2+1);//491
           alert(i2-1);//48
           var i3="a";
           alert(i3+1);//a1
           alert(i3-1);//Nan，表示不是一个数字
        </script>
```

- 等号
  - =：赋值；
  - ==：比较的是值，即数字类型也可以和字符串进行比较；
  - ===：比较的是值和类型，即只有类型相同才可以进行比较；

```html
<script type="text/javascript">
            var i=10;
            var x="20";
            if(i==="10"){
                alert(10);
            }else{
                alert(123);
            }
        </script>
```

补充：

- 直接向页面输出的语句，即可以向页面输出变量，固定值和html代码；
  - document.write(“aaa”);
  - document.write(“< br/ >”);
  - document.write(“< hr/ >”);

> document.write里面是双引号，如果想要设置标签的属性，需要使用单引号；
>
> document.write可以输出变量，还可以输出html代码；

#### js的数组

定义方式

- 方式一：var arr=[1,3,5];   var arr=[1,3,”5”,true,3.14]

- 方式二：使用内置对象Array对象--先定义长度，在填充

- 方法三；使用内置对象Array--定义数组的同时填充内容

  ```html
  	<script type="text/javascript">
              //方法一
              var arr1=[1,3,5,true,"A"];
             // alert(arr1);
              //方法二
              var arr2=new Array(3);
              arr2[0]=1;
              arr2[1]=2;
              arr2[2]=3;
              alert(arr2);
              //方法三
              var arr3=new Array(1,6,6,6,6);
              alert(arr3);
              alert(arr3.length);
          </script>
  ```

>  数组长度：数组名.length

#### js的函数/方法

- 参数列表中不需要写var，可以直接写变量；

- 方法一：使用关键字function

  - function 方法名（参数列表）{方法体；返回值可有可无}

  ```html
  <script type="text/javascript">
              //定义一个三个数相乘的方法
              function method(a,b,c){
                  var sum=a+b+c;
                  alert(sum);
              }
              //调用
              method(2,3,5)
          </script>
  ```

  - 匿名方法；var 自定义名称=function(参数列表){方法体和返回值；}

  ```html
  <script type="text/javascript">
              //定义一个三个数相乘的方法
              var method=function method(a,b,c){//
                  var sum=a+b+c;
                  alert(sum);
              }
              //调用
              method(2,3,5)
          </script>
  ```

  - 方法三：【了解】：使用到js里面的一个内置对象Function
    - var  自定义名称=new  Function(“参数列表”，“方法体和返回值”)

#### js的全局变量和局部变量

- 全局变量：在script标签里面定义一个变量，这个变量在页面中js部分都可以使用
- 局部变量：在方法内部定义一个变量，只能在方法内部使用；

> ie自带了一个调试工具，ie8及其以上的版本，F12；

#### js标签的位置

- 理论上放到哪里都可以，即使是< /script >的结尾后面，但是建议吧script标签放到< /body > 后面；
- 如果你想要在js中获取input里面的值，但是script标签放的是head里面，此时我们无法取到里面的值；因为html是从上到下解析的，你把script标签放到head里面，而input是需要放到body里面的，这样当我们想要获取值的时候，页面还没有解析到input那一行，就无法取到；