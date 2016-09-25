## 摘要
------
### 1.作业L1 在屏幕上让你的英文名字水平移动起来
### 2.作业L2 在80*80点阵上用字符拼出你想画的东西，并让它旋转起来，希望脑洞大开！（比如字符、火柴人、火箭等等）

## 背景
------
> *  在课程主页上复习这两次课程的内容，初步掌握python和matplotlib的语法规则，为接下来的课程做好准备,并完成此次作业。

## 正文
------
>  *  作业1：在屏幕上让自己的英文名水平移动

### 代码如下：

```python
import os
import time
qwhitespace = ['        ', '        ', '        ', '        ', '        ', '        ', '        ']
def kunnoname(name, lens):
    qA = ['   #    ', ' #   #  ', '#     # ', '# ### # ', '#     # ', '#     # ', '#     # ']
    qB = [' #####  ', '#     # ', '#     # ', '######  ', '#     # ', '#     # ', ' #####  ']
    qC = [' #####  ', '#     # ', '#       ', '#       ', '#       ', '#     # ', ' #####  ']
    qD = ['######  ', '#     # ', '#     # ', '#     # ', '#     # ', '#     # ', '######  ']
    qE = ['####### ', '#       ', '#       ', '######  ', '#       ', '#       ', '####### '] 
    qF = ['####### ', '#       ', '#       ', '#####   ', '#       ', '#       ', '#       ']
    qG = [' #####  ', '#       ', '#       ', '#   ### ', '#     # ', '#    ## ', ' #### # ']
    qH = ['#     # ', '#     # ', '#     # ', '####### ', '#     # ', '#     # ', '#     # ']
    qI = [' #####  ', '   #    ', '   #    ', '   #    ', '   #    ', '   #    ', ' #####  ']
    qJ = ['  ##### ', '     #  ', '     #  ', '     #  ', '     #  ', ' #   #  ', '  ###   ']
    qK = ['#     # ', '#    #  ', '#   #   ', '####    ', '#   #   ', '#    #  ', '#     # ']
    qL = [' #      ', ' #      ', ' #      ', ' #      ', ' #      ', ' #      ', ' #####  ']
    qM = ['#     # ', '##   ## ', '# # # # ', '#  #  # ', '#     # ', '#     # ', '#     # '] 
    qN = ['#     # ', '##    # ', '# #   # ', '#  #  # ', '#   # # ', '#    ## ', '#     # ']
    qO = [' #####  ', '#     # ', '#     # ', '#     # ', '#     # ', '#     # ', ' #####  '] 
    qP = ['######  ', '#     # ', '#     # ', '######  ', '#       ', '#       ', '#       ']
    qQ = [' #####  ', '#     # ', '#     # ', '#     # ', '#   # # ', '#    #  ', ' #### # '] 
    qR = ['######  ', '#     # ', '#     # ', '######  ', '#   #   ', '#    #  ', '#     # '] 
    qS = [' ###### ', '#       ', '#       ', ' #####  ', '      # ', '      # ', '######  ']
    qT = ['####### ', '   #    ', '   #    ', '   #    ', '   #    ', '   #    ', '   #    ']
    qU = ['#     # ', '#     # ', '#     # ', '#     # ', '#     # ', '#     # ', ' #####  ']
    qV = ['#     # ', '#     # ', '#     # ', ' #   #  ', ' #   #  ', '  # #   ', '   #    ']
    qW = ['#     # ', '#     # ', '#  #  # ', '#  #  # ', '#  #  # ', '# # # # ', ' #   #  ']
    qX = ['#     # ', ' #   #  ', '  # #   ', '   #    ', '  # #   ', ' #   #  ', '#     # ']
    qY = ['#     # ', '#     # ', ' #   #  ', '  # #   ', '   #    ', '   #    ', '   #    ']
    qZ = ['####### ', '     #  ', '    #   ', '   #    ', '  #     ', ' #      ', '####### ']
    alphabet = {'whitespace':qwhitespace, 'a':qA, 'b':qB, 'c':qC, 'd':qD, 'e':qE, 'f':qF, 'g':qG, 'h':qH, 'i':qI, 'j':qJ, 'k':qK, 'l':qL, 'm':qM, 'n':qN, 'o':qO, 'p':qP, 'q':qQ, 'r':qR, 's':qS, 't':qT, 'u':qU, 'v':qV, 'w':qW, 'x':qX, 'y':qY, 'z':qZ}
    screen = [' ']*7
    for x in range(4):    
        for j in range(7):
            for i in range(lens):
                screen[j] =qwhitespace[0]*x + screen[j] + alphabet[name[i]][j]   #get your name use "#"
            print screen[j]   
            screen = [' ']*7
        time.sleep(0.3)
        os.system('cls')
        print ('\n')*2*x
    return screen 
    
def main():
    name = raw_input('please input your English name:')   
    lens = len(name)
    name = name.lower()  # exchange what you input into lower case letters
    kunnoname(name,lens)
main()
 ```
### 动图效果如下：  
![hjdshfjsa](https://github.com/Tuzexin/computationalphysics_N2014301020169/blob/master/john.gif)
 
 
>  *  作业2：字符移动

###  代码如下：

 ```python
    for x in range(4):    
        for j in range(7):
            for i in range(lens):
                screen[j] =qwhitespace[0]*x + screen[j] + alphabet[name[i]][j]   #get your name use "#"
            print screen[j]   
            screen = [' ']*7
        time.sleep(0.3)
        os.system('cls')
        print ('\n')*2*x
    return screen 
  ```
 
###  动图效果如下：
![gif]()
 
##  致谢
致谢马士全同学的帮助！
 
