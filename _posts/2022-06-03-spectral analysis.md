### 信号分析：为了获得时间和频域之间的相互关系；
### 傅里叶变换：提供频域信息，但有关时间变化的局部化信息基本丢失；

## 谱分析，是将时间序列用正弦和余弦的线性组合进行建模的思想，提供了非常容易地发现“隐藏”周期性的工具。 
## 谱分析是从寻找时间序列数据里“隐藏的周期性”开始的。时间序列的相关性质，常称作时间域上的分析。
 在对时间序列的频率性质进行分析时，我们称为在频率域上进行研究，频域分析或称谱分析，在诸如声学、通信工程、地球物理学、生物医学等各领域都特别有用。
 
## 谱分析是非常重要的时间序列和空间序列分析方法。（1）在时间序列分析中，这种方法叫做功率谱分析；（2）在空间序列分析中，该方法叫做波谱分析。谱分析是寻找周期、节律或趋势从而发现自然规律的有效工具，其原理貌似复杂，实际上不难理解。借助快速 Fourier 变换（ FFT）即可对时间序列进行功率谱分析，或者对空间系列进行波谱分析

## FFT
FFTs assume no missing data. Missing data destroys the symmetry that makes the "Fast" part of FFT work.
You haven't indicated your purpose, but basically, your options are:
1) Interpolate to fill the gaps before FFTing. If your gaps are irregular, this can be tedious; and you should do some tests with known
data to evaluate the effects of the interpolation. For example, take a complete image with properties similar to your data and delete 5% of the
data. Interpolate the gaps and then compare the FFTs of the original and interpolated images.

2) Use a curve-fitting routine, such as REGRESS, to fit sines and cosines. (Least-squares fitting with sines and cosines is equivalent to
the FFT when there is no missing data.) This is much slower than an FFT, but if your data size is not too large, you may not notice or care.
If you know ahead of time that you only want to keep a few frequencies, then this could be as fast as an FFT.

### 小波分析（英语：wavelet analysis）或小波变换（英语：wavelet transform）是指用有限长或快速衰减的“母小波”（mother wavelet）的振荡波形来表示信号。该波形被缩放和平移以匹配输入的信号。

## 小波变换：通过缩小 母小波 的宽度来获得信号的频率特征， 平移 母小波到某一个位置获得信号的时间信息，所以小波运算可以获取频域信息，还有时间方面信息。缩放和平移操作为了计算小波系数，小波系数反映了小波和局部信号之间的相关程度；
## 离散小波变换将一副图像分解为大小，位置和方向都不同的分量。一个图像做小波分解后，可以得到一系列 不同分辨率 的子图像，小波变换正是沿着多分辨率这条线发展起来的；
## 与傅里叶相比：

小波变换是时间和频率的局部化分析；通过伸缩平移运算对信号逐步进行多尺度细化；最终达到高频处时间细分，低频处频率细分；能自动适应时频信号分析的要求，从而可以聚焦到信号的任意细节，解决了傅里叶变换的困难问题；

小波：是一类在有限区间内快速衰减到0的函数，平均值为0，小波趋于不规则和不对称；

正弦波：从负无穷一直延续到正无穷，平滑且可以预测；

从小波和正弦波看出：变化剧烈的信号用不规则的小波分析比用平滑正弦波更好，用小波更能描述信号局部特征；

小波变换虽然取全部信息，但是小波衰减到0；只有移到小波中心位置附近的点，才有值；小波的值乘以信号的值，累加取和，就是小波系数

![image](https://user-images.githubusercontent.com/21980320/172716259-2962560f-a668-46eb-8736-99edaffa9e62.png)
![image](https://user-images.githubusercontent.com/21980320/172716660-78a5bc18-0192-4ff2-836c-f06aa52067cd.png)
