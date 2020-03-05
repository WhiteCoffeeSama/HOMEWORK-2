# 网络与分布式计算作业2

## 第一章课后题

### P8

> 假定用户共享一条3Mbps的链路。又设每个用户传输时要求150kbps，但是每个用户仅有10%的时间传输。  
> a. 当使用电路交换时，能够支持多少用户？  
> b. 对于本习题的后续小题，假定使用分组交换。求出某给定用户正在传输的概率。  
> c. 假定有120个用户。求出在任何给定时刻，实际有n个用户在同时传输的概率。(提示：使用二项式分布。)  
> d.求出有21个或更多用户同时传输的概率。

**解答：**

*a.* 3Mbps/150kbps=20  
当使用电路交换时，能够支持20个用户

*b.* 用户正在传输的概率为10%

*c.* P=$C_{120}^n$$P^n$$(1-P)^{120-n}$  
实际有n个用户在同时传输的概率为n!/120!$P^n$$(1-P)^{120-n}$

*d.* P=$\sum_{I=21}^{120}$$C_{120}^i$$P^i$$(1-P)^{120-i}$=1-$\sum_{i=0}^{20}$$C_{120}^i$$P^i$$(1-P)^{120-i}$  
根据中心极限定理得P=P(Z<=${9\over \sqrt[2]{120*0.1*0.9}}$ )=P(Z<=2.74)  
P约等于0.997，因此多于N用户发送数据的概率为0.003

---

### P10

> 考虑一个长度为L的分组从端系统A开始，经3段链路传送到目的端系统。令$d_{i}$、$s_{i}$和$R_{i}$表示链路i的长度、传播速度和传输速率(i = 1, 2, 3)。该分组交换机对每个分组的时延为$d_{proc}$。假定没有排队时延，用$d_{i}$、$s_{i}$、$R_{i}$(1, 2, 3）和L表示，该分组总的端到端时延是什么？现在假定该分组 是1500字节，在所有3条链路上的传播时延是$2.5*l0^{8}m/s$,所有3条链路的传输速率是2Mbps, 分组交换机的处理时延是3ms,第一段链路的长度是5000km,第二段链路的长度是4000km,并且最后一段链路的长度是1000km。对于这些值，该端到端时延为多少？

**解答：**

$d_{sum}$=$d_{trans}$+$d_{prop}$+$d_{proc}$+$d_{queue}$=(l/r1+l/r2+l/r3)+(d1/s1+d2/s2+d3/s3)+(2*$d_{proc}$)+0 = (3*1500*8b/2Mbps)+(5000km+4000km+1000km)/ 2.5*$10^8$m/s+3ms+3ms+0 = 0.018s+0.04s+6ms = 64ms  
该端到端时延为64ms。

---

### P25

> 假定两台主机A和B相隔$20000km$,由一条直接的$R=2Mbs$的链路相连。假定跨越该链路的传播速率是$2.5*l0^{8}m/s$。  
> a. 计算带宽-时延积$R*t_{prop}$  
> b. 考虑从主机A到主机B发送一个800 000比特的文件。假定该文件作为一个大的报文连续发送。 在任何给定的时间，在链路上具有的比特数量最大值是多少?  
> c. 给出带宽-时延积的一种解释。  
> d. 在该链路上一个比特的宽度（以米计）是多少？它比一个足球场更长吗？  
> e. 用传播速率$s$、带宽$R$和链路$m$的长度表示，推导出一个比特宽度的一般表示式。

**解答：**

*a.* $R*t_{prop}=R\frac{m}{s}=2Mbs*\frac{20000km}{2.5*10^{8}m/s}=160000bits$

*b.* 比特占满整个链路可得比特数最大为时延带宽积，即160000bits

*c.* 带宽-时延积也可以看作是链路上具有的比特数量的最大值

*d.* 20000000/160000 = 125m, 比足球场长

*f.* $m\div (R\times \frac{m}{s}) =s/R$