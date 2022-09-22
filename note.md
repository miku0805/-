哈尔滨工业大学 计算机网络(笔记)

### P4
ISP : 网络业务提供商(isp --> i -> internet s -> server p -> provider)
这个在中国就是移动，电信，联通
(不同等级的ISP逐层连接构成了我们现在的Internet)

### P5
N个节点互联 需要n(n-1)/2 条边 (N^2链路问题) --> 让计算机与交换设备链接(O(n)) --> 交换网络(支持动态转接，这样就不需要大量端口去一一匹配)

最典型的电路交换网络: 电话网络
资源独占(当双方都不说话的时候，信道仍被占用)

而电路交换网络的信道是可以被共享的，这种技术成为 "多路复用" 

### P6
多路复用技术通常有一下四类: 

(1)	频分 多路复用 : 有线电视网络
每个用户占用不同的频带

(2)时分 多路复用 
将时间化为帧 ，每个用户在每个帧中占用固定序列的时隙(周期性)

(3)波分 多路复用
光纤通信中多见,每个用户用不同波长的光(频率)

(4)码分 多路复用 
广泛用于无线链路共享(如蜂窝网络,卫星通信等)
每个用户分配一个唯一的 m bit码片序列(其中的0用-1,1用+1来表示)
各用户码片序列相互正交

### P7
报文交换(一次性的将一个文件(报文)转发到某个节点)
常见就是: 上世纪的电报

分组交换: 将报文拆分成一系列较小的数据包 --> 还要加上头部信息(产生额外开销)

分组交换也能信道共享: 报文片段会像队列一样被传输 , 叫 统计多路复用
但是A可能传输比B多(1010111) A->1 B->0 

报文交换 和 分组交换 都采用存储-转发的交换方式,只是
报文交换 以完整的报文进行
分组交换 以较小的分组进行

### P8

报文交换一次就是整个报文的存储与转发,所以服务器的缓存至少要是报文的大小

只考时延,分组交换的时间更低
<font color=#10aec2>(报文交换是串行的,而分组交换是并行传输的)</font>
且分组交换需要的缓存更小

结论: 分组交换更优于报文交换

### P9
电路交换使用 多路复用技术,但是信道资源会被占用(即使用户不活动),所以其用户数量有限。
而 分组交换所有人都是用的概率低,所以

 <font color=#10aec2>分组交换允许更多用户同时使用网络 </font>

但是可能产生拥塞 ---> 分组延迟和丢失 