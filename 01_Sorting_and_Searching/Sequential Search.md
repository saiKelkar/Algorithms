Steps: 
1. Check each array entry 0, 1, 2, 3, …
   for match with search string (called as key)
2. If match found, return index of matching string
3. If not, return -1

Model:
- N string on the whitelist (like a set A)
- cN transactions for constant c (like a universal set)
- (assume) string length not long

Analysis:
- A random search hit checks about half of the N strings on the whitelist, on average.
- A random search miss checks all of the N strings on the whitelist, on average.
- Expected order of growth of running time: $N^{2}$  