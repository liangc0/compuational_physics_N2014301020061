物基一班   梁曦璘    2014301020061

Week 11: Problem 3.31

一、题目内容：
       题目为一个给定初始速度和初始位置的质点在一个封闭图形围成的区域内运动，有碰撞则反弹的一个模型。研究质点的运动轨迹以及各方向速度与坐标的关系。

二、解题过程：
       首先先建立直角坐标系，为了方便起见，将图形的中心设为坐标原点。对于运动的质点，位置由坐标（x，y）表示，速度分解为沿x轴和沿y轴方向。为（vx，vy）。对于每一步的时间设为0.0001，因此每一步的长度会比较小，在研究碰撞的瞬间时不必考虑精确的碰撞点，只需把刚好超出边界的点定为碰撞点进行反弹。
       研究碰撞点时分为几类：①在正方形边界进行碰撞：若在x=±1的边界上碰撞，则碰撞后的速度为：（vx0，vy0）为碰撞前的速度

> vx=-vx0  ； vy=vy0

若在y=±1的边界上碰撞，则碰撞后的速度为：（vx0，vy0）为碰撞前的速度

> vx=vx0  ； vy=-vy0

②在圆的边界上碰撞，设碰撞前的点（即超出边界前一刻的点）位置为（p，q），碰撞的点（即超出边界那一刻的点）位置为（x0，y0）。则碰撞后的点（即反弹的后一刻的点）位置为（x，y）。有以下的关系：

> x=[p*(x0^2 + y0^2) + 2x0*y0*q] / (x0^2 + y0^2)
> y=[q*(-x0^2 + y0^2) + 2x0*y0*p] / (x0^2 + y0^2)

碰撞后的速度可以用以下关系式来计算：

> vx=(x-x0) / △t;    vy=(y-y0) / △t;

③在椭圆的边界上碰撞：碰撞的原理与在圆上的碰撞是一样的，公式有所改变，具体如下：

>  k= (a * a *y0) / (b*b*x0)
>  c= y0 - k*x0
>  x = (2*k*q -(k*k+1)*p -2*k*c) /(k*k-1)
>  y = (-2*k*p +(k*k +1) * q -2*c) / (k*k-1)

其中k，c对应的y=kx+c 为碰撞点的法线方程。

三、运行程序与结果表达
       对于第一个模型：一个边长为1的正方形以及在以正方形中心的半径为0.1的圆。
       质点初始位置为（0.1,0.1），初始速度（10,15），质点运动的图像如下：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_28.png?raw=true)
    当改变质点的初始位置为（0.3,0.2），初始速度不变，圆的半径为0.2，得到质点运动的图像：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_29.png?raw=true)

   保持初始状态不变，研究质点运动x坐标与x轴速度的关系：
   下面图为运动5万步的情况：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_30.png?raw=true)

  下面为运动50万步的情况：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_31.png?raw=true)


  对于第二个模型，为椭圆模型，长半轴为1，短半轴为0.99。初始位置为（0.1,0.1），初始速度为（10,15）。下面是运动10万步的情况：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_32.png?raw=true)

下面是运动30万步的情况：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_33.png?raw=true)

对于长半轴为1，短半轴为0.9的椭圆模型，研究质点初始位置为（0.1,0.1），初始速度为（10,15）的运动状态：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_34.png?raw=true)

质点运动y坐标与y轴速度的关系：（点为碰撞时的y坐标与y轴速度）
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_35.png?raw=true)
质点运动x坐标与x轴速度的关系：（点为碰撞时的x坐标与x轴速度）
       ![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_36.png?raw=true)


四、结论
    因此，我们从图像可以看出，模型1（正方形和圆形组合）中，粒子几乎可以到达可以到的地方，且运动是杂乱无章的。对于模型2（椭圆），粒子运动范围似乎受到限制，在椭圆和双曲线所划定的区域内运动。速度与位置的图像中，没有观察到混沌现象。

五、致谢：
Chapter 3 Oscillatory Motion and Chaos  

