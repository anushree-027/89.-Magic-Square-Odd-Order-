# 89.-Magic-Square-Odd-Order-
import numpy as np

order = int(input("Enter order of magic square (odd): "))
if order % 2 == 0:
    order += 1
    print("Given order is even, incremented by 1.")

magic = np.zeros((order, order), dtype=int)
i, j = 0, order // 2

for num in range(1, order*order + 1):
    magic[i][j] = num
    new_i, new_j = (i-1) % order, (j+1) % order
    if magic[new_i][new_j] != 0:
        i = (i+1) % order
    else:
        i, j = new_i, new_j

print("Generated Magic Square:\n")
for row in magic:
    print(" | ".join(f"{val:2d}" for val in row))
