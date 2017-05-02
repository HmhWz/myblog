---
title: es6的map和set
date: 2017-05-02 17:49:18
tags:
categories: js
---

## Map

初始化一个Map需要一个二维数组:
```bash
let lina = new Map([['name', 'lina'], ['gender', 'women'], ['age', 20]]);
lina.get('name'); // lina
```
Map实例具有以下方法：
<!--more-->
```bash
lina.set('ult', '神灭斩'); //set() 方法用来添加key-value
lina.has('ult'); //true  has()判断是否存在某个key
lina.get('gender'); //women  get()得到对应的value
lina.delete('ult'); //删除key 'ult'
lina.has('ult'); //false
```
注意，一个key只能对应一个value，所以对已经存在的key设置value会覆盖掉以前的值：
```bash
lina.set('age', 23);
lina.get('age'); //23
```

## Set
Set和Map类似，但是只有key没有value。而且key不能重复。
初始化Set需要一个数组：
```bash
let s = new Set(['3', 3, 1, 3]);
s; //Set {'3', 3, 1} 重复的元素自动被过滤
```
Set实例可以通过add()和delete()方法增删元素：
```bash
s.add(5); //Set {'3', 3, 1, 5}
s.delete(1);
s; //Set {'3', 3, 5}
```


