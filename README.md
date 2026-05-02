# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:

Python with NumPy and SciPy libraries.

# Program:

```

import numpy as np
import math 

L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples: "))

for i in range(n): 
    pr = float(input(f"Enter the probability of sample {i + 1}: "))  
    p.append(pr)

for j in range(n): 
    l = float(input(f"Enter the length of sample {j + 1}: "))  
    lk.append(l)

for k in range(n):
    Avg1 = p[k] * lk[k]
    L += Avg1

for k in range(n):
    e = p[k] * math.log(1 / p[k], 2)
    hs += e
hs = round(hs, 3)

eff = round(hs / L, 3)

red = round(1 - eff, 3)

var = 0
for k in range(n):
    var1 = p[k] * (lk[k] - L) ** 2
    var += var1
var = round(var, 3)


print()
print(f"Average Codeword Length:    {L}")
print(f"Entropy                :    {hs}")
print(f"Efficiency             :    {eff}")
print(f"Redundancy             :    {red}")
print(f"Variance               :    {var}")


```

# Calculation:



# Output

<img width="781" height="538" alt="Screenshot_2026-05-02_11-37-50" src="https://github.com/user-attachments/assets/d839a32d-463f-4872-84b3-a6ddcb5e6dbc" />

# Results:


The Huffman and Shannon-Fano coding techniques have been successfully applied to the given source. The average codeword length, entropy, variance, redundancy, and efficiency have been computed.
