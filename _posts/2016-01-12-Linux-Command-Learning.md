---
layout: post
title: Linux Shell Command Learning(1)
---

### awk
打印第n列：
```
awk '{print $n;}'
```

### ps
查看进程信息：
```
ps aux
```
查看进程的可执行文件的位置：
```
pwdx PID
```
查看多个进程的可执行文件位置：
```
pwdx `ps aux | grep expr | awk '{print $2;}'`
```
这样是把后面命令的输出结果作为pwdx的参数，注意区分参数和STDIN的区别
