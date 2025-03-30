# EXP N0-08 HAMMING-SHANNON-FANON
### Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
### Apply the Huffman and Shannon-Fano to this source. 

### Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

### Aim :

To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

### Tools Required : 

python IDE with Numpy and Scipy.

### Program : 
~~~python 
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
~~~

### Calculation : 

![image](https://github.com/user-attachments/assets/7d478f1c-1728-4153-9d17-e643b0fb6326)
![Image 2025-03-25 at 20 50 53_e864d568](https://github.com/user-attachments/assets/4aa688b9-2c25-444c-9c30-ed8be17b73f6)
![Image 2025-03-25 at 20 50 54_9686ec27](https://github.com/user-attachments/assets/b09c5b08-7e87-4096-aa28-9267966578fa)
![Image 2025-03-25 at 20 53 22_ad08f113](https://github.com/user-attachments/assets/db1b4b90-aaa9-4bbc-8907-6c43fef441a0)
![Image 2025-03-25 at 20 53 53_7383a1d1](https://github.com/user-attachments/assets/967b9733-fcfd-4790-b160-d1ca00591e9a)

### Results :

For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25
Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484
