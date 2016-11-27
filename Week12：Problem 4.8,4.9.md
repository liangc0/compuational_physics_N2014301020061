物基一班   梁曦璘    2014301020061

Week 12: Problem 4.8,4.9

一、题目内容：
       题目4.8：在八大行星中验证开普勒第三定律的成立。
       题目4.9：如果万有引力定律为F=GMeMs/R^β（β≠2），那么行星运动的轨迹会变成什么样子。

二、背景：
       开普勒第三定律为：T^2/a^3=k（常数），其中T为行星运动的椭圆的周期，a为椭圆的长半轴。![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/059010459e171957fa0eb3d38c84978f.jpg?raw=true)
       我们以地球与太阳所组成的系统为研究对象，地球围绕着太阳转。由万有引力提供向心力有，GMeMs/R^2=Mev^2/R，即当地球以v=（GMs/R）^1/2的速度运行时，为圆周运动。当初速度不是这个值时，会以椭圆的轨迹运动（前提是没有其他星球的影响）。那么，此时开普勒第三定律依然成立。
      万有引力定律是一个经验定律，由开普勒经过多次观察后的数据总结得出的。若万有引力定律公式不是r的-2次项，而是β次项，那么行星的运行轨迹将不会是圆或者椭圆。

三、解题过程：
       首先先建立直角坐标系，为了方便起见，将太阳设为坐标原点。用Euler-Cromer法把地球（星球）的运动轨迹和速度进行分解，代入万有引力公式有：

 - vx[i]=vx[i-1] - 4 *π^2 * x[i-1] / (ri ^ 3) *dt
 - x[i]=x[i-1] + vx[i-1] * dt
 - vy[i]=vy[i-1] - 4 *π^2 * y[i-1] / (ri ^ 3) *dt
 - y[i]=y[i-1] + vy[i-1] * dt

对于构造椭圆轨迹，只需稍微改变初始速度即可。
对于长轴和短轴的计算，为：

 - a = (xmax - xmin) / 2
   b = (ymax - ymin) / 2
   其中xmax为坐标中x的最大值，xmin为坐标中x的最小值,ymax为坐标中y的最大值，ymin为坐标中y的最小值。

对于开普勒第三定律的验证，我用了两种方法：
    ①运用开普勒第二定律（面积定律），即单位时间内扫过的面积是相同的，计算出扫过一个椭圆的面积需要的时间T。
    ②通过运行程序，得到行星运动一圈所需的时间T。

对于4.9题：只需改变β，并且改变不同的初始速度，相应的公式改为：

 - vx[i]=vx[i-1] - 4 *π^2 * x[i-1] / (ri ^ （1+β）) *dt
 - x[i]=x[i-1] + vx[i-1] * dt
 - vy[i]=vy[i-1] - 4 *π^2 * y[i-1] / (ri ^ （1+β）) *dt
 - y[i]=y[i-1] + vy[i-1] * dt

四、运行程序与结果表达
           对于4.8题：[程序](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/Program4.8)
       用两种方法进行计算，其中初始速度设为1.01*v0，v0为作圆周运动时的速度。时间间隔约为1%周期。
       得到结果如下：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/%E6%90%9C%E7%8B%97%E6%88%AA%E5%9B%BE20161127200337.png?raw=true)
   
对于4.9题：[程序](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/Program%204.9)
首先，先不改变初始速度，为v0，经过调试程序后发现当β接近2时根本没有出现奇怪的现象。当β变为2.5时，发现一个周期时出现了发散现象：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_39.png?raw=true)
β为3时，现象更加明显：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_40.png?raw=true)

然后，改变初始速度，为1.01v0。当β=2.5时，在一个周期时出现的发散现象比初速度为v0时更加明显：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_41.png?raw=true)
多运行几个周期，得到很明显的轨迹不重合的现象：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_42.png?raw=true)

接着，改变初始速度，为1.1v0。当β=2.5时，在一个周期时出现的发散现象比初速度为1.01v0时更加明显，并且还发现了周期明显变短的现象：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_44.png?raw=true)
并且研究了β=1.9时的现象：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_47.png?raw=true)
以及β=1.5时的现象：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_48.png?raw=true)

最后奉上初速度为1.3v0，β=2.1时行星运行的漂亮轨迹：![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_46.png?raw=true)



五、结论
    对于4.8题，经过模拟，我们发现：结果与书上提供的权威答案并不一致，原因可能如下：①程序模拟的是行星绕太阳运动时的二体运动情况，把其它干扰的作用力全部排除，但实际上行星运动会受到其它形式的作用力，周期和长轴会与模拟的有所不同。②程序中没有考虑相对论效应。

对于4.9题，经过模拟，我们发现：当β不为2时星球会以非几何的轨迹进行运行，偏离2越大，情况更加明显，且出现发散的现象。而且当初速度有所变化时（即β=2时沿椭圆轨迹运行），变化越大，偏离的现象也更加明显，且周期也会相应地发生变化。

六、致谢：
Chapter 4 The Solar System

