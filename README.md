# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
colab matplotlib
# Program:
#Huffman and Shannon-Fano coding
```
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
# Calculation:
```
<img width="1189" height="990" alt="dc - exp -2" src="https://github.com/user-attachments/assets/946302c0-03d1-46fe-b710-e90f9d1ec19a" />

```
# Output
```
<img width="1189" height="990" alt="dc - exp -2" src="https://github.com/user-attachments/assets/68295ec3-baab-4128-a4bb-e8b15eb7fc50" />
<img width="1114" height="191" alt="Screenshot 2025-09-09 110028" src="https://github.com/user-attachments/assets/7d2a1439-8116-42ec-b85f-fb79765f9126" />


``` 
# Results:
```
For the given discrete memoryless source with probabilities {0.125,0.0625,0.25,0.0625,0.125,0.125,0.25}, both Huffman and Shannon–Fano coding were applied. The simulation was carried out in Python (Google Colab). Since the source probabilities are exact powers of two, the codeword lengths match the ideal values, giving zero redundancy and 100% coding efficiency. Both Huffman and Shannon–Fano yield identical results.
```
