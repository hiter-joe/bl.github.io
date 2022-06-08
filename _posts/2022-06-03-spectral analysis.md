### 谱分析，是将时间序列用正弦和余弦的线性组合进行建模的思想，提供了非常容易地发现“隐藏”周期性的工具。
 
### 谱分析是从寻找时间序列数据里“隐藏的周期性”开始的。时间序列的相关性质，常称作时间域上的分析。
 在对时间序列的频率性质进行分析时，我们称为在频率域上进行研究，频域分析或称谱分析，在诸如声学、通信工程、地球物理学、生物医学等各领域都特别有用。
 
### 谱分析是非常重要的时间序列和空间序列分析方法。（1）在时间序列分析中，这种方法叫做功率谱分析；（2）在空间序列分析中，该方法叫做波谱分析。谱分析是寻找周期、节律或趋势从而发现自然规律的有效工具，其原理貌似复杂，实际上不难理解。借助快速 Fourier 变换（ FFT）即可对时间序列进行功率谱分析，或者对空间系列进行波谱分析

## FFT

FFTs assume no missing data. Missing data destroys the symmetry that makes the "Fast" part of FFT work.

You haven't indicated your purpose, but basically, your options are:

1) Interpolate to fill the gaps before FFTing. If your gaps are
irregular, this can be tedious; and you should do some tests with known
data to evaluate the effects of the interpolation. For example, take a
complete image with properties similar to your data and delete 5% of the
data. Interpolate the gaps and then compare the FFTs of the original
and interpolated images.

2) Use a curve-fitting routine, such as REGRESS, to fit sines and
cosines. (Least-squares fitting with sines and cosines is equivalent to
the FFT when there is no missing data.) This is much slower than an
FFT, but if your data size is not too large, you may not notice or care.
If you know ahead of time that you only want to keep a few frequencies,
then this could be as fast as an FFT.

## 小波分析（英语：wavelet analysis）或小波变换（英语：wavelet transform）是指用有限长或快速衰减的“母小波”（mother wavelet）的振荡波形来表示信号。该波形被缩放和平移以匹配输入的信号。

小波变化的发展，承袭Gabor transform的局部化思想，并且克服了傅里叶和Gabor transform的部分缺陷，小波变换提供了一个可以调变的时频窗口，窗口的宽度(width)随着频率变化，频率增高时，时间窗口的宽度就会变窄，以提高分辨率．小波在整个时间范围内的振幅平均值为0，具有有限的持续时间和突变的频率与震幅，可以是不规则，或不对称的信号。

小波变换分成两个大类：离散小波变换（DWT） 和连续小波变换（CWT）。两者的主要区别在于，连续变换在所有可能的缩放和平移上操作，而离散变换采用所有缩放和平移值的特定子集。
![image](https://user-images.githubusercontent.com/21980320/172716259-2962560f-a668-46eb-8736-99edaffa9e62.png)
![image](https://user-images.githubusercontent.com/21980320/172716660-78a5bc18-0192-4ff2-836c-f06aa52067cd.png)
