物基一班   梁曦璘    2014301020061

Homework 08: Problem 3.10

一、题目内容：
       研究做简谐振动的单摆在一系列的阻力下的振动情况，研究FD不同的情况下振动情况的异同

二、解题过程：
        运用Euler法，将单摆的位置用角度表示，并将角度与角速度分离，分别写出其关系式。具体
初始状态：

>         self.xita = [0.2]
        self.oumiga = [0]

其它不变的初始条件：

> q = 1/2
        oumuD = 2/3
        length=1
        garvity=9.8
        dt=0.04

运行程序主体（初始设置和输出部分略去）：
>         for i in range(self.nsteps):
             oumiga1 = self.oumiga[i] - self.g* sin(self.xita[i])* self.dt/ self.l 
               - self.q *self.oumiga[i] *self.dt + self.FD* sin(self.oumuD *self.t[i]) *self.dt
               
             xita1 = self.xita[i] + oumiga1* self.dt
             self.oumiga.append(oumiga1)
             self.xita.append(xita1)
             self.t.append(self.t[i] + self.dt)

做出图像Θ与t的关系图Θ（t）
 
三、结果表达
       首先，将FD=0.1代入，得到图像![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_10%EF%BC%88fd=%E3%80%821%EF%BC%89.png?raw=true)
然后，将FD=0.5代入，得到图像![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_9%EF%BC%88fd=%E3%80%825%EF%BC%89.png?raw=true)
再将FD=0.99代入，得到图像![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_8%EF%BC%88fd=%E3%80%8299%EF%BC%89.png?raw=true)
最后，我们将所有的图像放在一起比较，有![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_7.png?raw=true)
（其中，蓝色线的是FD=0.1的图像，绿色线的是FD=0.5的图像，红色线的是FD=0.99的图像）

四、结论
因此，我们可以得出：在时间比较小的区间内，小球的角度摆动是混乱的，无法预测，不是规则的简谐振动；当时间比较长的区间内，小球的角度摆动可以近似看为简谐的。
    但是，FD参数（FD<1）的改变对小球摆动的角度有极大的影响。具体如下：①在时间少的混沌区间里，我们无法预测小球摆动的角度峰值与FD的影响，但是，FD越大，处于混沌区间的时间越短，即更早进入可近似看为简谐振动的区间。②在类简谐振动的区间，FD越大，角度的峰值越大。

五、致谢：
Chapter 3 Oscillatory Motion and Chaos  