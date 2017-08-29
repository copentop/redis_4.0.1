## redis code



### OOM

Linux 内核有个机制叫OOM killer（Out-Of-Memory killer），该机制会监控那些占用内存过大，尤其是瞬间很快消耗大量内存的进程，为了防止内存耗尽而内核会把该进程杀掉。


```
zmalloc.c

zmalloc_default_oom

```


### RSS

VSS- Virtual Set Size 虚拟耗用内存（包含共享库占用的内存）

RSS- Resident Set Size 实际使用物理内存（包含共享库占用的内存）

PSS- Proportional Set Size 实际使用的物理内存（比例分配共享库占用的内存）

USS- Unique Set Size 进程独自占用的物理内存（不包含共享库占用的内存）


一般来说内存占用大小有如下规律：VSS >= RSS >= PSS >= USS