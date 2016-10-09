# Abstract
------
By the drawing function of Matplotlib insde the Python and the numerical approach, we can learn the decay process of radioactive particles.
# Background
------
Consider again a decay problem with two types of nuclei A and B, but now suppose that nuclei of type A decay into ones of type B, while nuclei of type B decay into ones of type A. Solve this system of equations for the numbers of nuclei. Strictly speaking, this is not a "decay" process, since it is possible for the type B nuclei to turn back into type A nuclei. A better ananlogy would be a resonance in which a system can tunnel or move back and forth between two states A and B which have equal enerdies. The corresponding rate equations are:
![picture 1](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B71.PNG)

where for simplicity we have assumed thet the two types of decay are characterized by the same time constant, τ.
# Main body
------
We can know that the The radioactive decay process satisfies the equation：

![picture 2](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B72.PNG)

where the N is the number of the nuclear, τ is the time constant for the decay.   It's easy to get the solution:

![picture 3](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B73.PNG)

In order to learn the process in a numerical apporach, we can make a Taylor expansion to N:

![picture 4](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B74.PNG)

use the Euler method :

![picture 5](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B75.PNG)

According to:

![picture 1](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B71.PNG)

Slove the Differential Equations:

![picture 6](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B76.PNG)

So we have the numeber of expressions of A and B：

![picture 7](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B77.PNG)

#Code
------
```python
import pylab as pl
class uranium_decay_A_and_B:
    N_A = input("Input Initial number of nuclei_A :")
    N_B = input("Input Initial number of nuclei_B :")
    tc = input("Input time constant :")
    tod = input("input time of duration :")
    ts = input("Input time step :")
    def __init__(self, number_of_nuclei_A = N_A, number_of_nuclei_B = N_B, time_constant = tc, time_of_duration = tod, time_step = ts):
        # unit of time is second
        self.n_uranium_A = [number_of_nuclei_A]
        self.n_uranium_B = [number_of_nuclei_B]
        self.init_A = number_of_nuclei_A
        self.init_B = number_of_nuclei_B
        self.t = [0]
        self.tau = time_constant
        self.dt = time_step
        self.time = time_of_duration
        self.nsteps = int(time_of_duration // time_step + 1)
        print("Initial number of nuclei_A ->", number_of_nuclei_A)
        print("Initial number of nuclei_B ->", number_of_nuclei_B)
        print("Time constant ->", time_constant)
        print("time step -> ", time_step)
        print("total time -> ", time_of_duration)
    def calculate(self):
        for i in range(self.nsteps):
            tmp_A = self.n_uranium_A[i] + ((self.n_uranium_B[i] + self.n_uranium_A[i]) / self.tau - 2 * self.n_uranium_A[i] / self.tau )* self.dt
            tmp_B = self.n_uranium_B[i] + ((self.n_uranium_A[i] + self.n_uranium_B[i]) / self.tau - 2 * self.n_uranium_B[i] / self.tau )* self.dt
            self.n_uranium_A.append(tmp_A)
            self.n_uranium_B.append(tmp_B)
            self.t.append(self.t[i] + self.dt) 
    def show_results(self):
        pl.plot(self.t, self.n_uranium_A, 'b', label = "$N_A$")
        pl.plot(self.t, self.n_uranium_B, 'r', label = "$N_B$")
        pl.xlabel('time ($s$)')
        pl.ylabel('Number of Nuclei')
        pl.xlim(0, self.time)
        pl.legend()
        pl.show()
a = uranium_decay_A_and_B()
a.calculate()
a.show_results()
```
And the initial conditions can be changed via the keyboard input:  
```python
    N_A = input("Input Initial number of nuclei_A ->")
    N_B = input("Input Initial number of nuclei_B ->")
    tc = input("Input time constant ->")
    tod = input("input time of duration ->")
    ts = input("Input time step ->")
```
# Result of Code
When N_A = 100, N_B = 0, τ=1(s):

![picture 8](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B78.PNG)

When N_A = 100, N_B = 0, τ=0.5(s):It's obviously that the sysytem reached equilirium more quickly.

![picture 9](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B79.PNG)

When N_A = 100, N_B = 0, τ=2(s):It's obviously that the sysytem reached equilirium more slowly.

![picture 10](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/%E6%8D%95%E8%8E%B710.jpg)


#Conclusion
------
In fact, errors always exist in calculating and plotting even precision drafting by computer. However, these errors can usually be controlled and reduced to a negligible level that not affect results.

#References and Thanks
[How to think like a computer scientist – Learning with Python: Interactive Edition 2.0](http://interactivepython.org/runestone/static/thinkcspy/index.html)  
[teaching plan of Chapter 1](https://www.evernote.com/shard/s140/sh/d351f9a3-8076-4274-944b-7043e0ce8cf3/4f89e8630604ea23262f00b3ed11f8ad)  
[Matplotlib Tutorial](https://www.evernote.com/shard/s140/sh/d13e46ed-7170-4c8f-8792-48cc84d67473/a24cb1d43b9a6504626d97ac279078c0)

Thanks for MQdtc's help.


