Iterable:
- Allows for direct control of object iteration for more custom behaviour.
- Depends on both data structure and iterator.

Iterators:
- There are many data structures that exist, such as arrays, array lists and linked lists, various types of trees, hash maps, and more. 
- One common operation that might need to be done is to go through all of the items in the data structure. 
- However, with the different types of data structures, we would need to write different code for potentially each data structure. (Instead of doing this, an iterator could be used to go through the data structure -- abstracts the process of scanning through a sequence of nodes once.)
- Iterators -- special class / object that allows the user to easily traverse a data structure. 
- Iterators -- usually have methods to get the current item, go to the next item, or go to the previous item. 
- In C++  (implemented as types - usually classes or structs)
```
std::vector, std::list

it != container.end (checks if more elements exist)
*it++ (returns current element and advances)
it = container.erase(it) (removes current element)
```

```
std::vector<std::string> list = {"a", "b", "c"};
for(auto it = list.begin(); it != list.end(); ++it) {
	std::cout << *it << std::endl;
}
```

E.g. linked lists -- imagine we have a chain of boxes, and each box contains:
- some data (like number or a word)
- a link to the next box

```
[10 | next] --> [20 | next] --> [30 | NULL]
```

Why use a linked list?
- we can easily add or remove items in the middle or end without shifting all the elements.
- great for dynamic memory where size can grow or shrink. 
- but accessing an element is slower (we must follow the chain).
- we can't directly access, say, the 5th item -- must go one by one

Implementation in C++ (a simple singly linked list, i.e., only next pointers)
```
struct Node {
	int data;
	Node* next;
	Node(int value) {
		data = value;
		next = nullptr;
	}
};

// linked list class
class LinkedList {
private:
	Node* head;

public:
	LinkedList() {
		head = nullptr;
	}

	// Add to end
	void append(int value) {
		Node* newNode = new Node(value);
		if(head == nullptr) {
			head = newNode;
			return;
		}

		Node* current = head;
		while(current -> next != nullptr) {
			current = current -> next;
		}
		current -> next = newNode;
	}

	// Print the list
	void print() {
		Node* current = head;
		while(current != nullptr) {
			std::cout << current -> data << " -> ";
			current = current -> next;
		}
		std::cout << "NULL\n";
	}

	// Destructor to clean memory
	~LinkedList() {
		Node* current = head;
		while(current != nullptr) {
			Node* temp = current;
			current = current -> next;
			delete temp;
		}
	}
};

// Usage
int main() {
	LinkedList list;
	list.append(10);
	list.append(20);
	list.append(30);

	list.print(); // Output: 10 -> 20 -> 30 -> NULL
	return 0;
}
```

For-Each loop in C++
- Way to loop through all elements in a container (like array, vector, etc.) without writing an index manually. 

```
for(datatype variable : container) {
	// use variable
}
```

```
#include <iostream>

int main() {
	int numbers[] = {10, 20, 30, 40};

	for(int num : numbers) {
		std::cout << num << " ";
	}
	
	return 0;
}
```

```
#include <iostream>
#include <vector>

int main() {
	std::vector<std::string> fruits = {"apple", "banana", "cherry"};

	for(std::string fruit : fruits) {
		std::cout << fruit << "\n";
	}
	return 0;
}
```

```
// modifying elements
for(int& num : numbers) {
	num *= 2; // changes the original array value
}
```

Fancy Iterators:
- It is possible for data structures to implement different types of iterators.
- For example, in the case of lists, a data structure may implement one iterator that goes from the first to last element of the list and another iterator that goes from last to first element of the list. 
- In the case of trees, there may be pre-order, in-order, post-order, and level order iterators. 

Performance:
- In most cases, using an iterator will have the same or better time complexity than using other methods.