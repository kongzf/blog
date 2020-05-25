---
title: Jconsole远程监控
date: 12-2018-12-25 09:23:2208-2903-0711-0312-0508-2708-2809-1508-2904-1609-1208-2610-2412-0311-2109-0206-1804-1403-1302-2702-2803-0103-0103-0103-0305-2303-0403-0403-0503-0803-0803-0803-0804-2503-1003-1003-1203-1303-1903-2203-23
tags: 
categories: 
---

<!--more-->

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
![jconsole远程连接](https://img-blog.csdnimg.cn/20181224173142314.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxODY2OTQz,size_16,color_FFFFFF,t_70)  
点击连接即可：  
![连接成功](https://img-blog.csdnimg.cn/20181224184342186.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMxODY2OTQz,size_16,color_FFFFFF,t_70)