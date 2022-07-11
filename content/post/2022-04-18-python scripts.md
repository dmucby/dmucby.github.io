---
title:      "Python Script Study"
subtitle:   "Basic learning of python script"
description: "Python 核心语法脚本"
excerpt: ""
date:       2022-04-18 15:00:00
author:     "Boyu Cai"
image: "/img/programming/script/post-bg-unix-linux.jpg"
published: true
tags:
    - Scripts
URL: "/2022/04/18/script/python"
categories: [ "Tech" ]
---

# Python Script

## 核心语法

### 注释

```python
#!/usr/bin/python3

# 第一个注释

'''
注释
'''

print("Hello,Python!")
```

> * 复杂项目
> * 长期维护



### 输入输出

#### python实现

```python
str = input("please input:")
print()
```

#### bash实现

```bash
echo "please input"
read str
```



### if逻辑

```python
if command:
	x
elif command2:
    y
else:
```



### 文件读写

#### 获取所有内容

```python
file = fopen("filename")
lines = file.read() 
# lines = file.readline() 只读一行
print(lines)
```



### 函数

```python
def function(parameters):
    "函数文档
    function_work
    return
```



### 导入包

```python
import sys
```



### 常用模块

#### 获取命令行参数(sys)

```python
import sys

print('Number of arguments:',len(sys.argv))
print('Argument list :',str(sys.argv))
```

输出结果：

```bash
python3 script-io.py 1 a
Number of arguments: 3
Argument list : ['script-io.py', '1', 'a']
```

#### open

```python
with open('data.txt') as f:
    print(f.read())

with open('data.txt',mode='w') as f:
    f.write('this is the new content will write to the file')
```



#### os

```python
>>> import os
>>> entries = os.listdir() # 当前目录
>>> entries 
['script-io.py', 'filename']
```





















