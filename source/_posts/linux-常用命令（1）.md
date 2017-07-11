---
title: linux 常用命令(1)
date: 2017-07-11 11:57:02
tags:
categories: linux
---
## ls  用于列出文件：
### ls -a
列出所有文件，包括文件名以圆点开头的默认会被隐藏的文件。
### ls -d
与-l结合使用可以查看所指定目录的详细信息
### ls -r
以相反的顺序来显示结果，通常，ls命令的输出结果按照字母升序排列。<!--more-->
### ls -t
按照修改时间来排序
### ls -S
输出结果按照文件大小排序
### 例如将桌面的文件全部列出：
```bash
hmh@hmh-ubuntu:~$ cd 桌面
hmh@hmh-ubuntu:~/桌面$ ls -l
总用量 240
drwxrwxr-x  9 hmh hmh   4096 4月  12 22:08 blog_system
-rwxr-xr-x  1 hmh hmh    235 6月  22 21:42 eclipse.desktop
drwxrwxr-x  8 hmh hmh   4096 3月  12 14:40 express_blog
-rwxrwxr-x  1 hmh hmh    149 5月   6 11:32 hello.py
-rw-rw-r--  1 hmh hmh  23395 6月  21 22:26 jianli.docx
drwxrwxr-x  8 hmh hmh   4096 6月  16 13:17 music_im
drwxrwxr-x  9 hmh hmh   4096 4月  11 13:16 myblog
-rw-rw-r--  1 hmh hmh    376 5月  10 23:29 task in this term
-rw-rw-r--  1 hmh hmh    332 5月   2 18:37 test.js
-rwxrwxr-x  1 hmh hmh   4203 4月   3 13:58 unity-tweak-tool.desktop
drwxrwxr-x 10 hmh hmh   4096 4月  17 16:36 Vdo
drwx------  7 hmh hmh   4096 4月  16 11:02 Vue-cnodejs-master
drwxrwxr-x  8 hmh hmh   4096 4月  17 13:06 vue-mobile-qq
drwx------  8 hmh hmh   4096 4月  16 21:12 vue-music-master
-rw-rw-r--  1 hmh hmh    213 7月   5 23:23 warning
-rwxrwxr-x  1 hmh hmh    738 4月   3 13:58 wps-office-et.desktop
-rwxrwxr-x  1 hmh hmh    826 4月   3 13:58 wps-office-wpp.desktop
-rwxrwxr-x  1 hmh hmh    781 4月   3 13:57 wps-office-wps.desktop
drwxrwxr-x  7 hmh hmh   4096 4月  17 13:02 you-draw-i-guess
-rw-rw-r--  1 hmh hmh 135465 5月   5 17:29 计算机课程体系.jpg
hmh@hmh-ubuntu:~/桌面$ 
```
第一个字符表示文件类型，'d'表示是一个目录，'-'表示是一个普通文件，其后三个字符表示文件所有者的访问权限，再后三个字符表示
文件所属组中成员的访问权限，最后三个字符是其他所有人的访问权限。数字表示文件的硬链接数目。两个'hmh'分别表示所属用户和所属用户组的名字。然后是文件的字节数，最后修改文件的时间日期，最后是文件名。
## file命令用于打印出文件内容的简单描述。例如：
```bash
hmh@hmh-ubuntu:~/桌面$ file hello.py
hello.py: ASCII text
hmh@hmh-ubuntu:~/桌面$ file test.js
test.js: UTF-8 Unicode text
hmh@hmh-ubuntu:~/桌面$ file myblog
myblog: directory
hmh@hmh-ubuntu:~/桌面$ file jianli.docx
jianli.docx: Zip archive data, at least v1.0 to extract
hmh@hmh-ubuntu:~/桌面$ file 计算机课程体系.jpg
计算机课程体系.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 96x96, segment length 16, baseline, precision 8, 1293x740, frames 3
hmh@hmh-ubuntu:~/桌面$ 
```