---
title: Jconsole远程监控
date: 2018-12-25 09:23:22
comments: true #是否可评论  
toc: true #是否显示文章目录  
categories: "java" #分类  
tags:  
 - java  
 - 监控 
---

--------------------------------------------------------------------------------------------------------------------------------------

Jconsole远程监控
============

开发排查问题有时候需要监控jvm的内存线程等情况，可以通过java自带的jconsole工具来监控查看。

远程tomcat设置
----------

在远程tomcat的bin目录下，增加setenv.sh文件，脚本内容为：

    JAVA_OPTS="-Djava.rmi.server.hostname=192.168.46.11 -Dcom.sun.management.jmxremote.port=8099 -Dcom.sun.management.jmxremote.rmi.port=8099 -Dcom.sun.management.jmxremote.ssl=false -Dcom.sun.management.jmxremote.authenticate=false"
    

解释说明：

    1.-Djava.rmi.server.hostname=192.168.46.11 远程调用地址
    2.-Dcom.sun.management.jmxremote.port=8099 远程调用端口
    3.-Dcom.sun.management.jmxremote.ssl=false 是否https安全连接
    4.-Dcom.sun.management.jmxremote.authenticate=false 连接是否需要认证
    

本地jconsole设置
------------

在jdk安装目录下找到jconsole.exe，打开，  
![jconsole远程连接](https://camo.githubusercontent.com/727497b88592565ede18ad23768b87bc9cb8e2ca/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303138313232343137333134323331342e706e673f782d6f73732d70726f636573733d696d6167652f77617465726d61726b2c747970655f5a6d46755a33706f5a57356e6147567064476b2c736861646f775f31302c746578745f6148523063484d364c7939696247396e4c6d4e7a5a473475626d56304c334678587a4d784f4459324f54517a2c73697a655f31362c636f6c6f725f4646464646462c745f3730,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxODY2OTQz,size_16,color_FFFFFF,t_70)  
点击连接即可：  
![连接成功](https://img-blog.csdnimg.cn/20181224184342186.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxODY2OTQz,size_16,color_FFFFFF,t_70)
