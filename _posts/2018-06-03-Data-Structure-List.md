---
layout:     post   				                    # 使用的布局（不需要改）
title:      Data Structure - List 				    # 标题 
subtitle:   List, Stack, Queue and Implementation   # 副标题
date:       2018-06-03			                    # 时间
author:     Fanne 						            # 作者
header-img: img/OriginalList.png                    # 这篇文章标题背景图片
catalog: true 						                # 是否归档
tags:								                # 标签
    - Technology
---

## Data Structure - List 

***

### Overview 

* Abstract Data Type

* List and Implementation - Array or Linked Node

* Stack, Queue and Deque

* Standard Library (API)

    1. Java - Class: ArrayList, LinkedList, Stack; Interface: Queue, Deque
    
    2. Python - List (use as List, Stack, and Queue)

* References



### Abstract Data Type 

> "A class of objects, whose logical behavior is defined by a set of values and a set of operations."

An abstract data type is a logical concept, which defines how to organize and operate the original data. However, it does not define how to implement itself in a specific programming language. 

List, Stack, Queue and Deque are all abstract data types.



### List

> List is a sequence of items/data where positional order matters. 

Operations of List inlcudes: 

* get(pos): return value of the item at a sepecific position

* search(value): if the item exists, return the item, else return null

* insert(value, pos): inseart an item at a sepecific position

* remove(pos): remove an item at a specific position



#### Implementation - Array 

One important assumption: 

* We assume the array is **compact**, which means contiguous in memory. If there are N items in a size M array (M ≥ N), then only index [0..N-1] are occupied and other indices [N..M-1] should remain empty.

Two important features: 

* get the value in O(1) if you know the position (index) of the value. 

* **fixed** length once the array is created, which means if you want to increase the size, you have to copy all the values to a new and larger array.

![Array List](https://FanneYang.github.io/img/ArrayList.png)

Time complexity of each operation is as below: 

| Operations    | Best O(n)     | Worst O(n)    |
| ------------- | ------------- | ------------- |
| get           | O(1)          | O(1)          |
| search        | O(1): i = 0   | O(n): i = n-1 |
| insert        | O(1): i = n   | O(n): i = 0   |
| remove        | O(1): i = n-1 | O(n): i = 0   |

Fast when **get** and fair enough when **search**.

Slow when **insert** and **remove** with countless **RESIZE、COPYING、SHIFTING、and WASTED SPACE**!

![Array List](https://FanneYang.github.io/img/ArrayListOp.png)



#### Implementation - Linked Node 

Motivation:

* Flexiable Size

* Non-contiguous in memory

**Note:** 

You cannot get the item in O(1) even if you know the position (index) of the item. You have to search for it first!

![Linked List](https://FanneYang.github.io/img/LinkedListOp.png)

Time complexity of each operation is as below: 

| Operations    | Best O(n)     | Worst O(n)    |
| ------------- | ------------- | ------------- |
| get           | O(n)          | O(n)          |
| search        | O(1): i = 0   | O(n): i = n-1 |
| insert        | O(n): i = n   | O(1): i = 0   |
| remove        | O(n): i = n-1 | O(1): i = 0   |


