---
title: linux 常用命令(2)
date: 2017-07-15 20:10:57
tags:
categories: linux
---
## type：显示命令类型
```bash
hmh@hmh-ubuntu:~$ type cp
cp 是 /bin/cp
hmh@hmh-ubuntu:~$ type cd
cd 是 shell 内建
hmh@hmh-ubuntu:~$ type ls
ls 是 `ls --color=auto' 的别名
hmh@hmh-ubuntu:~$ type node
node 是 /home/hmh/.nvm/versions/node/v8.0.0/bin/node
hmh@hmh-ubuntu:~$ type java
java 是 /opt/jdk1.8.0_121/bin/java
```
<!--more-->
## which：显示一个可执行程序的位置，但不包含shell內建命令
```bash
hmh@hmh-ubuntu:~$ which ls
/bin/ls
hmh@hmh-ubuntu:~$ which cd
hmh@hmh-ubuntu:~$ which type
hmh@hmh-ubuntu:~$ which which
/usr/bin/which
hmh@hmh-ubuntu:~$ which node
/home/hmh/.nvm/versions/node/v8.0.0/bin/node
hmh@hmh-ubuntu:~$ which n
/home/hmh/Softwares/node/bin/n
hmh@hmh-ubuntu:~$ which javac
/opt/jdk1.8.0_121/bin/javac
hmh@hmh-ubuntu:~$ 
```
## help：得到內建命令的帮助文档
```bash
hmh@hmh-ubuntu:~$ help cd
cd: cd [-L|[-P [-e]] [-@]] [dir]
    Change ……
```
## man：显示程序手册页
## info：显示程序info条目
## wc：显示文件所包含的行数、字数和字节数。例如：
```bash
hmh@hmh-ubuntu:~$ wc 桌面/hello.py
  8  11 154 桌面/hello.py
hmh@hmh-ubuntu:~$ 
```
## grep：打印匹配行
```bash
hmh@hmh-ubuntu:~$ ls | grep [arm]
Android
AndroidStudioProjects
EclipseProjects
Games
IdeaProjects
MyProjects
node_modules
PycharmProjects
ReactNativeProjects
Softwares
WebstormProjects
hmh@hmh-ubuntu:~$ 
```
上面这个例子打印了所有包含字符'a'或'r'或'm'的匹配项。-i 选项使得忽略大小写，-v打印不匹配的行。
## head：打印文件头部n行
```bash
hmh@hmh-ubuntu:~$ head -n 3 桌面/test.js
let lina = new Map([['name', 'lina'], ['gender', 'women'], ['age', 20]]);

lina.set('ult', '神灭斩'); //set() 方法用来添加key-value
hmh@hmh-ubuntu:~$ 
```
上面这个例子打印了test.js的头3行。-n指定行数，默认为10行。
还可以这么用：
```bash
hmh@hmh-ubuntu:~$ ls -l | head -n 12
总用量 96
drwxrwxr-x  3 hmh hmh  4096 6月  22 00:49 Android
drwxrwxr-x 17 hmh hmh  4096 7月   1 13:53 AndroidStudioProjects
drwxrwxr-x  9 hmh hmh  4096 6月  20 20:47 EclipseProjects
drwxrwxr-x  3 hmh hmh  4096 7月  17 16:46 Games
drwxrwxr-x  3 hmh hmh  4096 7月  11 07:50 IdeaProjects
drwxrwxr-x  6 hmh hmh  4096 6月  18 16:34 MyProjects
drwxrwxr-x  8 hmh hmh 12288 7月  13 22:07 node_modules
drwxrwxr-x  4 hmh hmh  4096 5月  13 20:32 PycharmProjects
drwxrwxr-x  6 hmh hmh  4096 7月  15 15:06 ReactNativeProjects
-rw-rw-r--  1 hmh hmh    17 7月  17 20:13 sdf.txt
drwxrwxr-x  8 hmh hmh  4096 7月   5 12:32 Softwares
hmh@hmh-ubuntu:~$ 
```
这里会将ls输出端接到head命令的输入端，所以这里打印了ls -l 命令输出数据的前12行。
## tail：与head使用方法类似，打印文件尾部n行
```bash
hmh@hmh-ubuntu:~$ tail -n 4 桌面/test.js
let a = lina.has('ult');

console.log(a)

hmh@hmh-ubuntu:~$ 
```
