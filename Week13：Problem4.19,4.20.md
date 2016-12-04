物基一班   梁曦璘    2014301020061

Week 13: Problem 4.19,4.20

一、题目内容：
       题目4.19：研究Hyperion绕Saturn运行时自身的运动形态在不同的初始条件下的情况与变化。
       题目4.20：研究这种情况下在无限定条件下的情况及分析其原因。

二、背景摘要：
       Hyperion（即土卫7）是一个呈橄榄球的星体，因此在研究时采用哑铃状的模型对其进行简化计算。并且对其自身的自旋也进行研究与模拟。在其质心的运动轨迹为圆时，其自旋的角度与时间的关系为：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_51.png?raw=true)
       在其质心的运动轨迹为椭圆时，其自旋的角度与时间的关系为：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_52.png?raw=true)
       在质心的运动轨迹为椭圆时，出现了混沌现象。我们也就对此混沌现象进行深入的探究与模拟。

三、解题过程：
对质心的运动进行研究：       
首先先建立直角坐标系，为了方便起见，将土星设为坐标原点。用Euler-Cromer法把土卫7的运动轨迹和速度进行分解，代入万有引力公式有：

 - vx[i]=vx[i-1] - 4 *π^2 * x[i-1] / (ri ^ 3) *dt
 - x[i]=x[i-1] + vx[i-1] * dt
 - vy[i]=vy[i-1] - 4 *π^2 * y[i-1] / (ri ^ 3) *dt
 - y[i]=y[i-1] + vy[i-1] * dt

对于构造椭圆轨迹，只需稍微改变初始速度即可。

对于自旋，采用Euler-Cromer法对角度和角速度进行分离，有：

 - dω/dt = -12π^2 / r^5 *(x*sinθ-y*cosθ)*(x*cosθy*sinθ)
 - dθ/dt = ω
 - 其中，r = (x^2 + y^2)^2


四、运行程序与结果表达
           程序如下：
           对于4.19题，先对θ1=0，θ2=0.01进行分析，得到结果：质心绕土星的轨迹为圆的状态下Δθ与时间t的关系图：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_53.png?raw=true)
           质心绕土星的轨迹为椭圆的状态下Δθ与时间t的关系图：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_54.png?raw=true)
           这里可以看到轨迹为椭圆时，出现了混沌现象。
           其中，对图像中的瑕疵的解释：为其中一个的角度超过π或-π，而另一个未超过π或-π导致的。
           对θ1=0，θ2=0.1进行分析，得到结果：质心绕土星的轨迹为椭圆的状态下Δθ与时间t的关系图：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_55.png?raw=true)
           对θ1=1，θ2=1.1进行分析，得到结果：质心绕土星的轨迹为椭圆的状态下Δθ与时间t的关系图：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_56.png?raw=true)

对于4.20题，当撤销π和-π这一个限制后，再进行模拟。对θ1=0，θ2=0.01进行分析，得到质心绕土星的轨迹为椭圆的状态下Δθ与时间t的关系图：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_57.png?raw=true)
很明显，在t约为2.8时出现了及其大的上升现象，因此研究了θ与时间t的关系图和ω与时间t的关系图，结果发现在t=2.8左右时，ω2发生了突变：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_59.png?raw=true)
混沌状态由此开始，
而ω1还是正常的周期性状态：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_60.png?raw=true)
这样就产生了Δθ的剧烈增加。


五、结论
    通过上面的分析与模拟，我们得出以下结论：①在行星运行轨道为圆时，基本上不会出现混沌现象，即自旋角度和角速度在时间下呈周期性变化。②当运行轨道为椭圆时，会出现混沌现象，且初始状态偏离得越厉害，出现混沌的时间越早，混乱程度也越大。

六、致谢：
Chapter 4 The Solar System

