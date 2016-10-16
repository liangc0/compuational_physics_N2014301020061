物基一班   梁曦璘    2014301020061

Homework 06: Problem 2.2

一、题目内容：
       研究在一群骑自行车的选手中，排在前面的选手与在中间的选手所消耗的能量，已知在中间的选手所受的阻力面积是前面的选手的0.7倍，问他们以13米每秒的速度骑行时的消耗能量的情况。

二、解题过程：
       运用欧拉法，速度的变化关系：v（i+1）=v（i）+ Pdt/mv（i）-cρAv²（i）dt/2m
       对于中间的选手，A‘=0.7A
       可推导出P‘=P - 0.15cρAv³（i）dt/m
[程序](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/Week%2006:%20Problem%202.2%20%28program%29)

三、结论
       运行后得到图像![enter image description here](https://raw.githubusercontent.com/liangc0/compuational_physics_N2014301020061/master/figure_3.png)

红色的线是前面的选手消耗的能量
蓝色的线是中间的选手消耗的能量
因此，我们可以得出：前面的选手所消耗的能量比中间的选手大，且若骑行的速度越快，所消耗的能量之差越大。

四、致谢：
Chapter 2 Realistic Projectile Motion 