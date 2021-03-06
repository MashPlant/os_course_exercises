在ucore lab的实验环境搭建中，使用的**非开源**软件是()

- [ ] eclipse CDT
- [x] Scitools Understand
- [ ] gcc
- [ ] qemu

>  Scitools Understand 是非开源软件，主要可以用于分析代码，可免费试用一段时间。

RISC-V CPU有多种特权模式，rcore lab中碰到和需要处理哪些特权模式()

- [x] M-mode
- [x] S-mode
- [ ] H-mode
- [x] U-mode

> rcore需要碰到和处理M/S/U-mode

多道批处理系统主要考虑的是____()
- [ ] 交互性
- [ ] 及时性
- [x] 系统效率
- [x] 吞吐量

> 解释：交互性和及时性是分时系统的主要特征。多道批处理系统主要考虑的是系统效率和系统的吞吐量。
以ucore OS为例（lab6实验）,这主要看你如何设计调度策略了，所以如果实现FCFS(先来想服务)调度算法，这可以更好地为多道批处理系统服务；如果实现时间片轮转（time-slice round robin）调度算法，则可以有比较好的交互性；如果采用多级反馈队列调度算法，则可以兼顾上述4个选项，但交互性用户程序获得CPU的优先级更高。

(西北工业大学)CPU执行操作系统代码的时候称为处理机处于（  ）
- [ ] 自由态
- [ ] 目态
- [x] 管态
- [ ] 就绪态

> （知识点：3.4系统调用）内核态又称为管态


在使能分页机制的情况下，更合适的外碎片整理方法是() s4

- [ ] 紧凑(compaction)
- [ ] 分区对换(Swapping in/out)
- [x] 都不是

> 分页方式不会有外碎片

连续内存分配算法First Fit的缺点是\_\_\_\_
- [ ] 算法复杂
- [ ] 大的空闲分区会被分割
- [x] 容易产生外部碎片
- [ ] 分配速度慢

> 解释：First Fit算法非常简单，分配速度也较快。但是First Fit不考虑实际的需求和找到的空闲分区的大小的匹配度，所以容易产生外部碎片。


连续内存分配算法Best Fit的缺点是\_\_\_\_
- [ ] 算法复杂
- [ ] 大的空闲分区会被分割
- [ ] 分配速度慢
- [x] 回收速度慢

> 解释：Best Fit算法也非常简单，分配速度较快。由于选取的空闲分区大小都很合适，所以基本不会出现大的空闲分区总是被分割的情况。但是在此算法中，内存回收则涉及了很多操作：判断左右邻居是否是空闲分区，如果不是，则插入此空闲分区到合适的地方，如果是则合并空闲块，并把合并后的结果插入到合适地方；但是由于空闲分区链不是按地址排序的，所以上述操作需要遍历几次链表用于查找和插入，速度较慢。

连续内存分配算法Worst Fit的缺点是\_\_\_\_
- [ ] 算法复杂
- [x] 大的空闲分区会被分割
- [ ] 分配速度慢
- [ ] 容易产生很小的空闲分区

> 解释：Worst Fit每次使用最大的空闲分区，按照需求分割相应的大小，所以会造成大的空闲分区总是被分割。其算法比较简单，分配速度也很快。

应用程序中的逻辑地址到物理内存中的物理地址的**转换机制建立**的过程发生\_\_\_\_程序过程中
- [ ] 编译
- [ ] 链接
- [x] 加载
- [ ] 运行

> 解释：在编译器编译和链接程序的过程中都只涉及到逻辑地址，跟机器的配置无关，这也是编译链接所生成的可执行文件可以直接在相同系统的其它机器上使用的原因。而在操作系统加载应用程序时，操作系统负责建立应用程序的段表或页表。将逻辑地址和实际物理地址对应起来，之后应用程序在运行过程中CPU才能根据逻辑地址通过段表或页表正确访问到物理地址。

关于分段系统和分页系统说法正确有\_\_\_\_。
- [x] 页是系统层面的内存管理的单位，分页的目的主要是由于操作系统管理的需要；段是编写程序层面的内存管理的单位,分段的目的主要是为了能更好地满足程序员开发的需要
- [x] 页的大小是固定的，而且由系统确定。段的长度却是不固定的，决定于程序员所编写的程序
- [x] 分段系统会产生外碎片，分页系统会产生内碎片
- [x] 分段可灵活的控制存取访问，可根据各段的特点决定访问权