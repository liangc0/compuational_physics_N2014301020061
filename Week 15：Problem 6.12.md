物基一班   梁曦璘    2014301020061

Week 15: Problem 6.12

一、题目内容：
       研究开始时两端固定的弦各位置的初始状态可以用吉他弦表示，即

> y（x）=x/x0 (x<x0时)
> y（x）=（L-x）/（L-x0） （x0<x<L时）

（其中x0为初始时刻振幅的最大点，L为弦长）
并且求解能量光谱，与弦开始时振幅分布为高斯分布的情况作对比。

二、解题过程：
        先求解弦的振动，使用的方法为一步步进行模拟：

> y(i,n+1) = 2[1 - r^2] y(i,n) - y(i,n-1) + r^2 [y(i+1,n) + y(i-1,n)]
> 其中i为各个位置，n为各个时刻；r = c*dt/dx （一般r取1较方便）

然后，取离弦的一端距离约5%的点的每个时刻的位置来研究，将它进行快速傅里叶变换（FFT）得到的即为能量光谱。通过图像比较初始时为吉他弦（实际可达到的弦状态）和初始时为高斯分布的弦（理想弦状态）时的能量光谱。

三、运行结果表达：
      初始时，设定弦长为1分成100格，即每个点对应的长度为0.01。初始时弦振幅位置的最高点对应的位置为0.5，即第50格。输入初始时（n=0）和第一个时刻时（n=1）的位置，从n=2开始模拟。运行800个时间点（n=800）。记录第5格的位置随时间变化的位置变化。
      初始时为高斯分布函数的弦振幅时的图像：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_74.png?raw=true)
      
初始时为吉他弦的弦振幅时的图像：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_75.png?raw=true)

再作快速傅里叶变换（使用Python自带库里的函数）
得到初始时为高斯分布函数的弦振幅时的能量光谱：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_71.png?raw=true)

得到初始时为吉他弦的弦振幅时的能量光谱：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_72.png?raw=true)

放在一起比较：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_73.png?raw=true)

可见，它们都是两边高，中间低。
因此，我们放大其中一边，以放大0—50为例，具体如下：
初始时为高斯分布函数的弦振幅时的能量光谱：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_68.png?raw=true)

初始时为吉他弦的弦振幅时的能量光谱：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_69.png?raw=true)

放在一起比较：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_70.png?raw=true)

经过比较，可以得出它们的相同点：在顶峰（极大值）所对应的频率必定是成比例的，它们之间的间隔相等。并且两种模型的顶峰的位置相同。各个峰之间是不连续的。
不同点：顶峰时的能量及其它们之间的趋势不同。

四、结论
    通过上面的分析与模拟，我们得出以下结论：初始状态不同的弦，振动时的图像是不一样的，但是，它们都呈周期性的图像，没有出现混沌现象。在做出能量光谱后，可以看到：顶峰出现时的频率和相对应的波长是有规律的，波长可以用λ=2L/m（m为正整数）来表示。

五、致谢：
Chapter 6 Waves

