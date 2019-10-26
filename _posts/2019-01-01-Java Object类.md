---
layout: post
---

Object类中的11个方法：

- public String **toString**()
- public final Class<?> **getClass**()
- protected Object **clone**() throws CloneNotSupportedException
- protected void **finalize**() throws Throwable
- public int **hashCode**()
- public boolean **equals**(Object obj)
- public final native void **notify**()
- public final native void **notifyAll**()
- public final native void **wait**() throws InterruptedException
- public final native void **wait**(long millis, int nanos) throws InterruptedException
- public final void **wait**(long millis) throws InterruptedException



#### 一、toString()：

**对象转字符串。**默认由类名加@加HashCode组成：

```java
    public String toString() {
        return getClass().getName() + "@" + Integer.toHexString(hashCode());
    }
```

#### 二、getClass()：

**获取该对象的类的Class对象。**可以创建一个类的多个对象，类型信息存储在方法区，对象存储在堆，并且，每个类都有一个与之对应的Class对象。

#### 三、clone()：

**克隆一个对象。**

- 通过Cloneable和`clone()`方法，默认为浅克隆（除非内部未使用引用类型，或引用类型都实现了Cloneable接口）。
- 实现Serializable接口，深克隆。

#### 四、finalize()：

**对象被GC前，回调该方法。**


#### 五、hashCode()：

**获取该对象的哈希码。**两个对象的HashCode相等，`equals()`不一定为true。两个对象的`equals()`为true，则HashCode相等。

#### 六、equals()：

**判断两个对象是否相等。**

- `==`：对于基本类型，比较值。对于引用类型，比较引用的内存地址。
- `equals()`：默认使用了`==`，实际上，我们重写该方法用来比较对象值是否相同。

#### 七、notify()：

唤醒一个正在等待该对象的锁的线程，随机唤醒。

理解这个方法，需要了解Java的锁机制，即Monitor相关知识。

#### 八、notifyAll()：

唤醒所有正在等待该对象的锁的线程。

#### 九、wait()：

使持有该对象的锁的线程，进入等待（WAITING）状态。

- 必须在同步代码中调用，即必须持有锁。
- 会释放锁。

#### 十、wait(long millis, int nanos)：

使持有该对象的锁的线程，进入超时等待（TIME_WAITING）状态。

- 必须在同步代码中调用，即必须持有锁。
- 会释放锁，并且在指定时间间隔后会重新获得锁。

#### 十一、wait(long millis)：

与上面的方法类似。




