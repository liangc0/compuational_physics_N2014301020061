物基一班   梁曦璘    2014301020061

Homework 07: Problem 2.10

一、题目内容：
       研究炮弹发射后受到空气阻力的影响时的飞行轨迹，空气阻力的影响包括空气阻力，海拔高度下的压强差带来的影响，风带来的阻力

二、解题过程：
        运用Euler法，将水平与竖直的速度和位移分离，分别写出其关系式。具体
初始状态：

>         self.vx4 = [initial_velocity* cos(angle)]
        self.vy4 = [initial_velocity* sin(angle)]
        self.x4  = [0]
        self.y4  = [0]

运行程序主体（初始设置和输出部分略去）：
>         while(self.y4[-1]>= 0):
            v = sqrt(self.vx4[-1] * self.vx4[-1] +self.vy4[-1]* self.vy4[-1])
            rou = (1- 0.0000222* self.y4[-1])
            rou = rou* rou* sqrt(rou)
            b2 = (0.0039 +0.0058 /(1+ exp((v-35)/5)))* rou
            self.x4.append(self.x4[-1] +self.vx4[-1] *self.dt)
            self.y4.append(self.y4[-1] +self.vy4[-1] *self.dt) 
            self.vx4.append(self.vx4[-1] -b2 *self.vx4[-1] *v *self.dt)
            self.vy4.append(self.vy4[-1] -self.g *self.dt -b2 *v *self.vy4[-1] *self.dt)
            self.t4.append(tt)
            tt += self.dt

以及确定落点

>     self.x4[-1]=(self.x4[-2]+ self.x4[-1]*(-self.y4[-1]/ self.y4[-2]))/((-self.y4[-1]/ self.y4[-2]) +1)
    self.y4[-1]=0

然后再将角度进行变化，做出图像
最后再将初速度进行变化，做出图像
 
三、结果表达
首先，我们与上次作业时不考虑风阻时作比较
运行后得到图像![](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_4.png?raw=true)
其中，蓝色的线是不考虑风阻时的运行轨迹；绿色的线是考虑风阻时的运行轨迹

将初始角度变化，运行后得到图像![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_5.png?raw=true)
其中，绿色的线是45°时的运行轨迹；蓝色的线是47°时的运行轨迹；红色的线是43°时的运行轨迹

将初始速度变化，运行后得到图像![enter image description here](https://github.com/liangc0/compuational_physics_N2014301020061/blob/master/figure_6.png?raw=true)
其中，绿色的线是525m/s时的运行轨迹；蓝色的线是500m/s时的运行轨迹；红色的线是475m/s时的运行轨迹

四、结论
因此，我们可以得出：考虑了风阻后，炮弹飞行的距离明显变短了。在其它因素不变的情况下，在±2°的误差下，打得最远的明显不是45°；在±5%的速度误差下，速度越大，打得越远（在初始速度相对较大的情况下）

五、致谢：
Chapter 2 Realistic Projectile Motion 