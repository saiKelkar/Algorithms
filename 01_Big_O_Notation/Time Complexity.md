Running Time -- (of an algorithm) is the period during which the computer is executing, and typically grows with the input size.

Average case runtime may be difficult to determine, and best case runtime is not really considered. 

Growth of functions:
Seven functions that describe growth of functions that often appear in algorithm analysis:
constant = 1
logarithmic = log n
linear = n
n-log-n = n log n
quadratic = $n^2$
cubic = $n^3$
exponential = $2^n$

![[Pasted image 20250703115806.png]]

Primitive operations:
- basic computations performed by an algorithm
- identifiable in pseudocode
- largely independent from the programming language
- example:
  - evaluating an expression
  - assigning a value to a variable
  - calling a method
  - returning from a method
- these functions are considered to run in O(1) time

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

------

Big O (O) -- Worst case
- Describes the upper bound
- Easier to analyse and approximate
- Tells us how bad it can get ("It won't be slower than this.")
- Example: (in linear search)
  - Best case -- found at index 0 (O(1))
  - Worst case -- found at last or not found at all --> O(n)

Omega (Ω) -- Best case
- Describes the lower bound
- Tells us how fast it can be ("It will be at least this fast")
- Example: (in linear search)
  - Best case is if the item is at the beginning  --> Ω(1)

Theta (Θ) - Average / Tight bound
- Describe both lower and upper bounds
- Tells us the exact growth rate, when best and worst cases are the same ("It will always be this, give or take")
- Example: 
  - If a function takes exactly 3n + 2 time, it's Θ(n)



