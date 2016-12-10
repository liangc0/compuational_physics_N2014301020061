物基一班   梁曦璘    2014301020061

Week 14: Problem 5.4

一、题目内容：
       在一对平板电容器（只取一维的电容器），在二维空间产生的电势的情况，以及改变电容器的参数时的情况。

二、解题过程：
        求解这类问题，在空间中的电势满足拉普拉斯方程：▽^2 V=0。对于此偏微分方程的求解，在计算机中进行模拟。对于各点的势能有公式（二维平面）：

> V(i,j) = [V(i-1,j) + V(i+1,j) + V(i,j-1) + V(i,j+1)] / 4

在详细计算中，先固定板上的电势值，确定边界条件：边界的势能为0。然后对空间上每一个点进行如上的计算，如此重复多次循环计算。（本题中对100*100的空间点进行了300次的重复计算）并且，在计算的过程中运用了Gauss-Seidel方法，即：

> V(i,j) = [Vnew(i-1,j) + Vold(i+1,j) + Vnew(i,j-1) + Vold(i,j+1)] / 4

即每次计算后把原来的数据覆盖，下一个数据使用刚刚计算出的数据进行计算。

三、运行结果表达：
       初始值的设定：令电容器分别在x=30和x=70，宽度从y=30至y=70。左边的电容器板电势为V=1，右边的电容器板电势为V=-1。
       开始模拟，输出时运用等压线来表示。得出的结果：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_61.png?raw=true)
（蓝色的是V=±0.2的电势，绿色的是V=±0.5的电势，红色的是V=±0.8的电势）

之后改变电容器的位置：在x=20和x=80，宽度与电势不变。得出的结果：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_62.png?raw=true)
（蓝色的是V=±0.2的电势，绿色的是V=±0.5的电势，红色的是V=±0.8的电势）

由上面的图像可知，在对称的电容器所激发的势场中，势能的绝对值大小分布呈对称性的。

多次改变电容器的位置，研究V=±0.5时的等压线，结果如下：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_63.png?raw=true)
（其中红色的是电容器位置为x=20,80时的情况，绿色的是电容器位置为x=30,70时的情况，蓝色的是电容器位置为x=40,60时的情况）

保持电容器的位置不变，为x=30,70。改变电容器的长度y，进行模拟，结果如下：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_64.png?raw=true)
（其中红色的是电容器长度为y从40至60时的情况，绿色的是电容器长度为y从30至70时的情况，蓝色的是电容器长度为y从20至80时的情况）

很明显，对称性仍存在，只是等压线被拉长了。

如果使电容器不对称，即电容器的长度一边为30至70，另一边为20至80。进行模拟，得到结果：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_65.png?raw=true)
（绿色的是V=±0.8的电势，红色的是V=±0.5的电势）

这样，对称性就被打破了。

最后，若把电容器的电势改为V=±2，研究V=1的等压线与当电容器的电势V=±1，研究V=0.5的等压线的关系（即电势比例相同时的等压线），结果如下：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_67.png?raw=true)
（绿色的是电容器的电势V=±1，对于V=0.5的等压线；红色的是电容器的电势V=±2，对于V=1的等压线）

由上面的图可以清晰看到，二者是重合的，也就说明了在对称的电容器系统中，空间中势能与电容器势能之比相同者，其空间位置必相同。


五、结论
    通过上面的分析与模拟，我们得出以下结论：①在对称放置的电容器系统中，空间的电势分布是对称的，等压线呈环状②在对称的电容器系统中，空间中势能与电容器势能之比相同者，其空间位置必相同。

六、致谢：
Chapter 5 Potentials and Fields

