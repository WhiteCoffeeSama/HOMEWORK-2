## P7
思路:本题主要考虑排队时延，传输时延，传播时延。

解：

t = (56\*8)/64\*(10^3)+(56\*8)/2\*(10^6)+10\*10^-3 = 17.224*10^-3 s =17.224 ms

---

## P10
思路:本题主要考虑传输时延，传播时延，处理时延，且每一段都有这些时延。

解：

t1 = (1500\*8)/(2\*10^6)+5000\*(10^3)/(2.5\*10^8)+3*10^-3 = 6ms +20ms+3ms = 29ms

t2 = (1500\*8)/(2\*10^6)+4000\*(10^3)/(2.5\*10^8)+3*10^-3 = 6ms+16ms+3ms = 25ms

t3 = (1500\*8)/(2\*10^6)+1000\*(10^3)/(2.5\*10^8)+3*10^-3 = 6ms + 4ms  =10ms

t = t1+t2+t3 = 29ms+25ms+13ms = 64ms

---
## P13
思路:分别分析每一个分组的排队时延，进行求和

解：

a.
第1个分组的排队时延为 0, 第2个 L/R, 第3个 2L/R，第i个(i-1)L/R,第N个 (N-1)L/R.
因此平均排队时延为 (L/R + 2L/R + … + (N-1)L/R) / N = (N-1)L/2R

b.
当下一批 N 个分组到达时已经过了LN/R秒，而一批中等待最久的分组传输完毕时间为(N-1)L/R+L/R = LN/R,因此下一批来时，上一批已全部传输完毕，平均排队时延依然为 (N-1)L/2R