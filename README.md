# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
colab

matplotlib
# Program:
```
import math

# Probabilities given
p = [0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25]

# Corresponding Huffman/Shannon-Fano code lengths
lk = [3, 4, 2, 4, 3, 3, 2]

n = len(p)

# Average Codeword Length
L = sum(p[k] * lk[k] for k in range(n))

# Entropy
hs = sum(p[k] * math.log(1 / p[k], 2) for k in range(n))
hs = round(hs, 3)

# Efficiency & Redundancy
eff = round(hs / L, 3)
red = round(1 - eff, 3)

# Variance of codeword length
var = sum(p[k] * (lk[k] - L) ** 2 for k in range(n))
var = round(var, 3)

print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff * 100}%")
print(f"Redundancy is : {red}")
print(f"Variance is : {var}")

```
# Calculation:
![WhatsApp Image 2025-08-31 at 17 44 01_7b693560](https://github.com/user-attachments/assets/8d113313-5fe3-455d-8c89-3ba037b58656)

![WhatsApp Image 2025-08-31 at 17 44 02_38d1e9c3](https://github.com/user-attachments/assets/e1bf3484-eb70-4835-a63f-419da745fe11)

![WhatsApp Image 2025-08-31 at 17 44 02_5fc4cc45](https://github.com/user-attachments/assets/df42b065-a496-48f2-a8f9-6774bb43a7bb)







# Output

<img width="357" height="112" alt="image" src="https://github.com/user-attachments/assets/75fc03e2-2e27-465f-ba97-a155790eab7e" />



# Results:

For the given discrete memoryless source with probabilities
{0.125,0.0625,0.25,0.0625,0.125,0.125,0.25},
both Huffman and Shannon–Fano coding were applied. The simulation was carried out in Python (Google Colab).
Since the source probabilities are exact powers of two, the codeword lengths match the ideal values, giving zero redundancy and 100% coding efficiency. Both Huffman and Shannon–Fano yield identical results.
