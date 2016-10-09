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
