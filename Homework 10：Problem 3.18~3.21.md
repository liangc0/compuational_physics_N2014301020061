物基一班   梁曦璘    2014301020061

Homework 10: Problem 3.18~3.21

一、题目内容：
       研究做简谐振动的单摆在一系列的阻力与动力下的振动情况，研究FD不同的情况下振动的Poincare section（3.18题），以及稍微改变ΩD情况下的Poincare section（3.19题），然后，做出Bifurcation diagram，即θ与FD的关系，并且求出δn=（Fn-Fn-1）/（Fn+1-Fn），（题目3.20）。最后，改变其它因素，观察Bifurcation diagram图像，看会有什么效果（题目3.21）

二、解题过程：
        运用Euler法，将单摆的位置用角度表示，并将角度与角速度分离，分别写出其关系式。
初始状态：

>         self.xita = [0.2]
        self.oumiga = [0]

对于题目3.18，改变FD，
其它不变的初始条件：

> q = 1/2
        oumuD = 2/3
        length=9.8
        garvity=9.8
        dt=0.04

运行程序主体（初始设置和输出部分略去）：
> for i in range(self.nsteps):
            
             oumiga1 = self.oumiga[i] - self.g* sin(self.xita[i])* self.dt/ self.l \
               - self.q *self.oumiga[i] *self.dt + self.FD* sin(self.oumuD *self.t[i]) *self.dt
             xita1 = self.xita[i] + oumiga1* self.dt
             if xita1>pi:
                 xita1 =xita1 - 2*pi
             if xita1<-pi :
                 xita1 = xita1 + 2*pi
             self.oumiga.append(oumiga1)
             self.xita.append(xita1)
             TT=(2*pi * self.N / self.oumuD)           
             if (self.t[i] + self.dt) > TT:
                 self.oumigaT.append(oumiga1)
                 self.xitaT.append(xita1)
                 self.N = self.N +1
             self.t.append(self.t[i] + self.dt)

做出图像ω与θ的关系图ω（θ），其中输出的满足2πn=ΩD*t
 （3.18题）改变FD，重新运行，得到不同的结果
  （3.19题）改变ΩD，重新运行，得到不同的结果

对于3.20题，我们再增加一个关于FD的循环，重复运行程序（这种做法需要运行程序多次，效率不高，花费时间相对较长），即可得出图像，并且对局部分岔点进行局部放大，可以得到Fn

对于3.21题，我们首先改变ΩD，取ΩD=2.01/3,2.05/3,1.95/3,1.8/3，运行程序，得出图像，并由图像得到的现象进一步修改FD的范围，得到更清楚的图像

然后只改变q，运行程序，得出图像，并由图像得到的现象进一步修改FD的范围，得到更清楚的图像

然后只改变初始角θ0，运行程序，得出图像，并由图像得到的现象进一步修改FD的范围，得到更清楚的图像

三、结果表达
       对于3.18题，首先，将FD=1.4代入，得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_10%EF%BC%88fd=1.4.png?raw=true)
可见，此状态下点可以认为集中在一个区域内
然后，将FD=1.44代入，得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_11%EF%BC%88fd=1.44.png?raw=true)
可见，此状态下点可以认为集中在两个区域内
再将FD=1.465代入，得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_12%EF%BC%88fd=1.465.png?raw=true)
可见，此状态下点可以认为集中在四个区域内

对于3.19题，首先，ΩD=2.00代入，得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_14%EF%BC%88oumuD=2.00.png?raw=true)
然后，ΩD=1.99代入，得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_13%EF%BC%88oumuD=1.99.png?raw=true)
最后，ΩD=2.01代入，得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_15%EF%BC%88oumuD=2.01.png?raw=true)

对于3.20题，首先将FD的范围定为1.4~1.5，间隔0.001，得出图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_16%EF%BC%881.4~1.5.png?raw=true)

然后我们可以从图像看到，在FD≈1.42处，出现分岔，周期由1变为2；在FD≈1.45处，出现分岔，周期由2变为4；在FD≈1.48处，出现分岔，周期由4变为2。进而对FD=1.42,1.45,1.48进行放大，故有：
将FD的范围定为1.41~1.43，间隔0.0001，得出图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_17%EF%BC%881.41~1.43.png?raw=true)
由图像我们可以得到F1=1.418

将FD的范围定为1.44~1.46，间隔0.0001，得出图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_18%EF%BC%881.44~1.46.png?raw=true)
由图像我们可以得到F2=1.453

将FD的范围定为1.47~1.49，间隔0.0001，得出图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_19%EF%BC%881.47~1.49%EF%BC%89.png?raw=true)
由图像我们可以得到F1=1.483

将FD的范围定为1.33~1.35，间隔0.0001，得出图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_20%EF%BC%881.32~1.35.png?raw=true)
由图像我们可以得到F0=1.340

由此可以算得δ1=2.229

对于3.21题，ΩD=2.01/3，运行程序后得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_21%EF%BC%88oumud=2.01.png?raw=true)
取ΩD=2.05/3，运行程序后得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_22%EF%BC%88oumud=2.05.png?raw=true)
取ΩD=1.95/3，运行程序后得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_23%EF%BC%88oumud=1.95.png?raw=true)
取ΩD=1.8/3，运行程序后得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_24%EF%BC%88oumud=1.8.png?raw=true)

然后将ΩD=2/3，取q=1.01/2，运行程序后得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_26%EF%BC%88q=1.01.png?raw=true)
再取q=1.1/2，运行程序后得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_25%EF%BC%88q=1.1.png?raw=true)
最后改变初始角为0.3，运行程序后得到图像
![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_27%EF%BC%88xita=0.3.png?raw=true)
四、结论
因此，我们可以得出：改变各种因素（如ΩD），Poincare section图像发生巨大的变化，周期发生改变。Bifurcation diagram图像都会改变，而且是无规律，无法预测。这说明了混沌系统中稍微改变一个参数或作出一点偏差，就会发生巨大的改变。

五、致谢：
Chapter 3 Oscillatory Motion and Chaos  

ps：由于我无法正确安装vpython，故无法使用vpython，请老师原谅