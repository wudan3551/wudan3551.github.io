---
layout: post
title: Linux Shell Command Learning(1)
---

### awk
��ӡ��n�У�
```
awk '{print $n;}'
```

### ps
�鿴������Ϣ��
```
ps aux
```
�鿴���̵Ŀ�ִ���ļ���λ�ã�
```
pwdx PID
```
�鿴������̵Ŀ�ִ���ļ�λ�ã�
```
pwdx `ps aux | grep expr | awk '{print $2;}'`
```
�����ǰѺ����������������Ϊpwdx�Ĳ�����ע�����ֲ�����STDIN������
