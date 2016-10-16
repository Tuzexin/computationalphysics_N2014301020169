# Abstract
------
*In this Report, I will show some codes which are used to slove some realistic projection motions. Along with the book, I will show you: Two-dimensional projectile motion with air resistance---Problem 2.9.

# Background
------
Calculate the trajectory of our cannon shell including both air drag and the reduced air density at high altitudes so that you can reproduce the results in Figure 2.5. Perform your calculation for different firing angles and determine the value of the angle that gives the maximum range.

![picture1](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B71.PNG)
 
FIGURE 2.5: Trajectory of a cannon shell with (solid curves) and without (dotted curves) the effect of the lower air density at high altitudes taken into account. In all cases the air resistance was included with 

![picture2](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B711.PNG)

and the initial speed was 700m/s. The lower two curves were for a firing angle 35°, while for the top curves it was 45°. Note that the x and y scales are different.

# Main body
------
Because of trajectory without the effet of the lower air density, so C(the drag cofficient)=0. While g(the gravity acceleration)=9.8, m(the mass of cannon shell)=100, ts(the time step)=1, v(the initial velocity)=700m/s. Then we run the following codes. We can get the answer and know the value of the angle that gives the maximum range.

#Code
------
```python
import pylab as pl
import math
class cannon_shell:
    print("C/m is around 4 * 10^(-5) in the earth.")
    g = input("Please type the gravity acceleration:")  
    m = input("Please type the mass of cannon shell:")
    ts = input("Please type the time step:")
    xi = input("Please type the initial position of x(km):")
    yi = input("Please type the initial position of y(km):")
    vxi = input("Please type the initial velocity of x(km/s):")
    vyi = input("Please type the initial velocity of y(km/s):")
    C = input("Please type the drag cofficient:")
    T_0 = input("Please type the sea level temperature:")
    def __init__(self, gravity_acceleration = g, mass = m,\
    time_step = ts, initial_x_position = xi,\
    initial_y_position = yi, initial_x_velocity = vxi,\
    initial_y_velocity = vyi, drag_coefficient = C, 
    sea_level_temperature = T_0): 
        self.x = [initial_x_position]
        self.y = [initial_y_position]
        self.vx = [initial_x_velocity]
        self.vy = [initial_y_velocity]
        self.m = mass
        self.g = gravity_acceleration
        self.ts = time_step
        self.C = [drag_coefficient]
        self.T_0 = sea_level_temperature
    def trajectory(self):
        while(self.y[-1] >= 0):
            self.C.append((self.C[-1]/1000) * math.pow(2.5, 1.0 - 0.0065 * self.y[-1]/ self.T_0))
            self.vx.append(self.vx[-1] - self.ts * (self.vx[-1] * self.C[-1] * math.pow(0.5, math.pow(2.0, self.vx[-1]) + math.pow(2.0, self.vy[-1]))/ (1000 * self.m)))
            self.vy.append(self.vy[-1] - (self.g/ 1000) * self.ts - self.ts * (self.vy[-1] * self.C[-1] * math.pow(0.5, math.pow(2.0, self.vx[-1]) + math.pow(2.0, self.vy[-1]))/ (1000 * self.m)))
            self.x.append(self.x[-1] + self.vx[-1] * self.ts)
            self.y.append(self.y[-1] + self.vy[-1] * self.ts)
    def show_results(self):
        font = {'family': 'serif',
                'color':  'green',
                'weight': 'normal',
                'size': 16,}
        pl.plot(self.x, self.y)
        pl.title('cannon shell trajectory', fontdict = font)
        pl.xlabel('x (km)')
        pl.ylabel('y (km)')
        pl.ylim(0, 30)
        pl.show()
a = cannon_shell()
a.trajectory()
a.show_results() 

#Conclusion
------

#References and Thanks
