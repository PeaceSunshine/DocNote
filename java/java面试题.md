# Java程序员面试宝典

### java的特性

封装,继承,多态，抽象

### new 和clone

1.**new** 分配内存-->调用构造函数，填充对象的各个域(初始化)--->构造方法返回对象构建完毕，引用地址发布到外部

2.**clone** 分配内存--->将原对象中的各个域填充到新对象的域---->构造方法返回对象构建完毕，引用地址发布到外部(**浅拷贝深拷贝**)         

### equals和hashCode

1. 如果两个对象相同(equls==true),那么返回的hashCode值一定要相同

2. 如果hashCode值相同,不一定相同

   **1.自反性 2.对称性 3.传递性 4.一致性**

## StringBuilder和+

+最终还是被转换成StringBuilder进行字符串连接,循环中使用+每次循环都会创建一个StringBuilder，会占用大量资源，降低了效率；+不要与StringBuilder混合使用会创建大量StringBuilder;  StringBuilder和StringBuffer功能基本一样,StringBuilder不是线程安全的,效率更高

## ==和 equals,常量池，=，new String()

==比较引用类型的地址；equals比较字符串内容，=赋值的字符串在常量池中,两个同样的字符串指向同一个地址；new创建同样内容的字符串地址也会不一样

## 时间对象

```java
Calendar cal=Calendar.getInstance();//获得Calendar实例
cal.getTimeInMillis()；//获得毫秒数
System.currentTimeMillis();
LocalDateTime dt=LocalDateTime.now();
```



## int和Integer

```java
Integer a = new Integer(3);
Integer b= 3; //3自动装箱成Integer
int c=3;
a==b; //false不是引用同一对象
a==c; //true a自动拆箱成int类型再和c比较


Integer  f1=100,f2=100,f3=150,f4=150;
f1==f2;  //true  如果整型字面量的值在-128-127之间不会new新的Integer对象，而是直接引用常量池中的Integer对象
f3==f4;  //false

```



## IO的几种类型的流

按照流的方向:输入流和输出流     	 

按照实现功能分:节点流(可以从一个特定地方读写数据,如FileReader);  处理流(对已存在的流的连接和封装,如BufferReader		          需要其它流对象作参数)

按照处理数据的单位:字节流(继承于InputStream和OutputStream)和字符流(继承于InputStreamReader和OutputStreamWriter)

![字符流和字节流](F:\gitLibrary\DocNote\java\字符流和字节流.png)

## 字节流转为字符流

字节输入流转字符通过InputStreamReader实现，构造函数传入InputStream对象

字节输出流转字符通过OutputStreamWriter实现，构造函数传入OutputStream对象