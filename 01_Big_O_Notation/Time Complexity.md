![[Pasted image 20250703011944.png]]

Big O notation -- how we measure how efficient an algorithm is, especially as the input size grows
(answers the question -- If I double the size of the input, how much more time or memory will my algorithm use?)

Big O measures:
- Time complexity -- how long it takes to run
- Space complexity -- how much memory it uses
This is expressed in terms of n (n -- size of input)

O(1) -- Constant time (e.g., accessing an array element)
Doesn't grow with input. Super fast.

O(log n) -- Logarithmic time (e.g., binary search)
Input gets cut in half each step. Very efficient.

O(n) -- Linear time (e.g., loop through an array)
Work grows directly with input size.

```
// O(n) - runs once for each element

void printAll(int arr[], int n) {
	for(int i = 0; i < n; i++) {
		std::cout << arr[i] << " ";
	}
}
```

O(n log n) -- Linearithmic time (e.g., merge sort, quick sort)
A bit slower than linear.

O($n^2$)  -- Quadratic time (e.g., nested loop - like bubble sort)
Very slow for big inputs.
```
//O(n^2) - because for every element, you're looping over all elements again

for(int i = 0; i < n; i++) {
	for(int j = 0; j < n; j++) {
		// something
	}
}
```

O($2^n$) -- Exponential time (e.g., recursive Fibonacci)
Extremely slow. Input size = death.

