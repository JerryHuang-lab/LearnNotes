# java基础

##  查看字节码

进入代码所在的磁盘 f:

拷贝target下classes路径

查看字节码 javap -v className

输出到本地文件 >> className.txt

1. 启动main函数

Java xxx.class

1. 编译txt生成的java文件

javac xxx.java 

javac  -parameters xxx.java  带parameters参数的编译

 

idea中添加编译参数





如果不加-parameters参数，反射获取接口方法中的参数名是无法获取的

 



 

不加入参数时class字节码



加入-parameters参数 class字节码为



1. 方法签名

包括：返回值、方法名、参数类型、参数顺序