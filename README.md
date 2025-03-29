# Huffman-Shannon_fano
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

## Aim
To apply Huffman and Shannon-Fano to the source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} using python.

## Tools Required
python IDE with Numpy and Scipy

## Program
```
#Huffman and Shannon-Fano coding
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
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```

## Calculation

![image](https://github.com/user-attachments/assets/da183f7b-74d8-46d0-8d76-afd7ac89abb6)

![image](https://github.com/user-attachments/assets/945039e5-2f29-4616-92ce-073affcdb80d)

![image](https://github.com/user-attachments/assets/f0f60251-bb47-47a9-b2b3-52b10ab554d7)

## Output

![Screenshot 2025-03-29 092141](https://github.com/user-attachments/assets/7f28a483-3849-4cab-b854-14a38572192f)

## Results
Huffman and Shannon-Fano for the source {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} is successfully applied and verified.
