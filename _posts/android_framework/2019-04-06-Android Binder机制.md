---
layout: post
category: Android Framework
---

## Binder驱动
运行在内核空间。
## 内存映射
将用户空间的一块内存区域映射到内核空间。
## 实现原理
首先 Binder 驱动在内核空间创建一个数据接收缓存区；

接着在内核空间开辟一块内核缓存区，建立内核缓存区和内核中数据接收缓存区之间的映射关系，以及内核中数据接收缓存区和接收进程用户空间地址的映射关
系；

发送方进程通过系统调用 `copy_from_user()` 将数据 copy 到内核中的内核缓存区，由于内核缓存区和接收进程的用户空间存在内存映射，因此也就相当于
把数据发送到了接收进程的用户空间，这样便完成了一次进程间的通信。

如图：
![Binder原理][Binder原理]

## 通信模型
**Client、Server、ServiceManager、Driver**之间的关系如图：
![通信模型][通信模型]


[Binder原理]:{{ site.url }}/assets/pics/61f03ecb-4561-4a3d-b279-ccfe6daa2585-519559.jpg
[通信模型]:{{ site.url }}/assets/pics/ed924599-a796-44b6-95d5-9b749108f919-519559.jpg
