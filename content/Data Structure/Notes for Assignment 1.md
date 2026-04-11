---
title:
draft: false
tags:
---
> [!Note]
> Here, we **only** contain part of the note that relates to this assignment's questions. So we'll ignore some concepts that are not that important.
## What is an Algorithm?
> An algorithm is a process or set of **rules** to be followed in calculations or other problem-solving operations, especially by a computer.

In other words, it's just a **program** that solves a specific problem, like sorting or searching...
## What is Pseudocode?

 > Pseudocode is a human-readable and **informal** description of a computer programme’s algorithm, blending **natural language** (English sentences) with **programming** structures (like if/else, for/while, etc.).

 In other words, there isn't any standard format for pseudocode. As long as you describe the logic clearly, any style is okay.

## What is a Pointer?
Inside the computer, each **variable** is a **data** stored inside a memory location. A memory location has a unique address that identifies it.

For example:
```cpp
int num = 123;
char ch = 'a';
bool flag = true;
```
And in the memory:

![[pointer_1.png  | 500]]

---
As for pointers, instead of storing the actual data, they store an **address**.

```cpp
char* p = &ch;
```

![[pointer_2.png   | 500]]

If we print a pointer directly, as expected, it's an **address**. But if we use `*`, we'll get the data of the thing it points to.

For the example above:
```cpp
cout << p; // 0x02
cout << *p; // a
```

---

For better understanding, let’s try to translate the symbols `*` and `&` into English:

|              `*`              |         `&`          |
| :---------------------------: | :------------------: |
|     create a **pointer**      | the **address** of X |
| the thing **pointed** to by X |                      |

For example:

| Code             | Translate                                                                  | Note                    |
| ---------------- | -------------------------------------------------------------------------- | ----------------------- |
| `char ch = 'a'`  | character named `ch` is set to `'a'`                                       | --                      |
| `char* p = &ch;` | character **pointer** named `p` is set to the **address** of `ch`          | `p` value is an address |
| `char y = *p`    | character named `y` is set to ***the thing pointed to*** by `p`(i.e. `ch`) | `y` is set to `'a'`     |
## Why use Pointer?

Usually, the parameter (the inputs) of a function is **called by value**, which means each parameter is a completely new variable, just copied the value of the original variable passed in. Any changes to the parameter in the function will not affect the original variable. 

However, if the parameter of a function is a **pointer** (`*`), we say it is **called by reference**. In this way, any changes to the parameter in the function directly affect the original variable.

As an example, the `Function(int n)` is called by value; and the `Function(int* n)` is called by reference.
![[pointer_3.png |  700]]

In data structures, any operations like creating a node, updating a value, or deleting a node need to directly change the original data to have actual effects. So all the data stores within a data structure are often **called by reference** (using pointers `*`).
## What is Object/Class?
In the real world, an apple is an object. Each apple shares some common variables, like colour and weight. And every apple can grow bigger, to gain more weight.

Just like this, we call every single apple an **object**, and they all belong to the same **class**, `Apple`.
```cpp
class Apple {
	// Member Variables
	string color;
	int weight;
	// Member Functions
	void Grow(int val) {
		weight += val; // Gain more weight
	}
}
```
For each object, we can access its member variables by `ObjectName.VariableName`, and using member functions by `ObjectName.FunctionName()`:
```
Apple apple1;
apple1.color = "red";
apple1.weight = 5;
apple.Grow(5); // Now, apple1.weight is 10
```
![[class_1.png | 400]]
However, when creating a pointer (`*`) to access member variables and calling member functions by reference, we use `->`.
```
Apple* apple2; // A pointer with the type of Apple
apple2 -> color = "green";
apple2 -> weight = 3;
apple2 -> Grow(2); // Now, apple2.weight is 5
```
The reason why we use `->` here instead of `.` is for convenience, to write less `*` (the thing **pointed** to by X) in code. The code above is equivalent to the following code:
```
Apple* apple2;
(*apple2).color = "green";
(*apple2).weight = 3;
(*apple2).Grow(2); // Now, apple2.weight is 5
```

In data structures, a linked list node, a stack/queue item, a disjoint set, or a tree node are all defined as a class. Since they are often called by reference (using pointers `*`), we need to access their members using `->`.
# 1. Linked List (Q1)

## What is a Linked List?
As the name suggests, it is a list of nodes linked with pointers.

A basic node contains the `data` we want to store, and a pointer `next` to locate the next node. By default, the `next` pointer is set to `nullptr`, which means the pointer points to nothing.

```cpp
ListNode* node;
node -> data = 10;
node -> next = nullptr;
```

![[linked_list_1.png | 250]]

Next, a linked list has many list nodes, each connected to the next. We also create a pointer called `head` or `first` to locate the first node of the list.
![[linked_list_2.png | 700]]
To go through the whole list, we can create a pointer that begins from `first` until the `next` value is `nullptr`.

```cpp
ListNode* ptr = first;
while(ptr != nullptr) {
	cout << ptr -> data; // print the current node data
	ptr = ptr -> next; // move to the next node
}
```

## Basic operations of Linked List
### Search a node
To search the first node of a certain value, we go through the whole list and compare it with the target value.
```cpp
ListNode* Search(int val) {
	ListNode* ptr = first;
	while(ptr != nullptr) {
		if (ptr -> data == val) { // found the value
			return ptr;
		}
		ptr = ptr -> next; // move to the next node
	}
	return nullptr; // cannot find the node
}
```
### Add a node
Imagine we are going to add a node **after** a node (let's call it A). We need two steps:
1. Set `next` of the new node to `next` of A.
2. Set `next` of A to the new node.

![[linked_list_3.png]]
```cpp
ListNode* A;
// Imagine we already find the A

ListNode* new_node;
new_node -> data = 7; // Initialize the data

/* Add the new node after A */
new_node -> next = A -> next; // Step 1
A -> next = new_node; // Step 2
```
### Delete a node
To delete a node (let's call it D), we also need two steps:
1. Find the D's previous node.
2. Change `next` of the previous node to `next` of D.

![[linked_list_4.png ]]
```cpp
ListNode* D;
// Imagine we have already found the D

/* Delete D */
// Step 1. Find the previous node
ListNode* pre = first;
while(pre -> next != D) {
	pre = pre -> next; // move to the next node
}
// Step 2
pre -> next = D -> next; 
```

[[Guidance & my answer for Assignment 1#<Question 1>|Back to Question 1]]
# 2. Stack (Q2)
## What is Stack?
In real life, when we have a stack of paper, we usually add new paper on top and remove the paper on top.

Similarly, in programming, a stack is a container that has some data. It has a maximum capacity (`MAX`). We also use a pointer `top` to locate the top data of the stack.

![[stack_1.png | 200]]
## Basic operations of Stack
The two basic operations of a stack are **push** (add an item to the top) and **pop** (remove an item from the top).

![[stack_2.png | 400]]
### Push
To push an item:
1. Check if the **maximum capacity** `MAX` of the stack is reached.
- If yes, we say stackoverflow.
- If not, the push could proceed.
1. Add an item to the top.
2. Update the `top` pointer.
![[stack_3.png | 400]]
### Pop
To pop an item:
1. Check if the stack is **empty**.
- If yes, we say stack **underflow**
- If not, the process could proceed.
2. Remove the item from the top.
3. Update the `top` pointer.
![[stack_4.png | 400]]
### LIFO(Last In First Out) Principle
Because the push and pop are always at the top, it's easy to see that the **last** element **pushed** onto the stack (3 in the example below) is the **first** to be **popped**.
![[stack_5.png | 700]]
[[Guidance & my answer for Assignment 1#<Question 2>|Back to Question 2]]
# 3. Queue (Q3)
## What is a Queue?
Similar to a **queue** at McDonald's in real life (assuming no one cuts the line). Several people can be added to the queue (called **enqueue**), and the first person will leave the queue (called **dequeue**) after ordering her food.
![[queue_1.png | 300]]
Similarly to a stack, it also has a maximum capacity (`MAX`). We use two pointers to locate the front and rear of the queue.
## Basic operations of the Queue
The two basic operations of a queue are **enqueue** (add an item to the rear) and **dequeue** (remove an item from the **front**).
![[queue_2.png]]

### FIFO(First In First Out) Principle

Unlike a stack, in a queue, the **first** element **enqueued** (1 in the example above) is the **first** to be **dequeued**. In other words: First-come, First-served.

[[Guidance & my answer for Assignment 1#<Question 3>|Back to Question 3]]
# 4. Big-Oh Analysis (Q4-Q7)
## How to predict the running time
Approximately, the computer takes the same amount of time to run each **basic operation**, including:

| Basic Operation                       | Sample         |
| ------------------------------------- | -------------- |
| Assigning a value to a variable       | `x=7;`         |
| Calling a function                    | `print("Hi");` |
| Arithmetic (e.g., adding two numbers) | `1+1`          |
| Comparing two numbers                 | `x < 5`        |
| Indexing into a Vector/Array          | `a[5]`         |
| Returning from a function             | `return x;`    |

Each of them count as "1 operation" (1ops).

So if we know the **relationship between the number of operation and the input**(usually use Math function $T(n)$ to represent), we can predict the running time when the input get larger.

For example, $n$ is an input, if $T(n)=2n^2+2n+1$, then:

| $n$ equals to | Total numbers of Operations              |
| ------------- | ---------------------------------------- |
| 1             | $2+2+1=5$                                |
| 2             | $2\times 2^2 + 2 \times 2 + 1 = 13$      |
| 100           | $2\times 100^2 + 2\times 100 + 1 =20201$ |
| ...           | ...                                      |

Then, if we know the running time of one input, we can predict others easily.

For the example above, if we also knows when $n=2$, the running time is $1.3~second$

i.e.

| $n$ equals to | Total numbers of Operations         | Running Time |
| ------------- | ----------------------------------- | ------------ |
| 2             | $2\times 2^2 + 2 \times 2 + 1 = 13$ | $1.3~second$ |

So each operation takes $1.3s/13=0.1~second$

To predict the running time of the input $n=100$:

| $n$ equals to | Total numbers of Operations              | Running Time                              |
| ------------- | ---------------------------------------- | ----------------------------------------- |
| 100           | $2\times 100^2 + 2\times 100 + 1 =20201$ | $20201 \times 0.1~second = 2020.1~second$ |

[[Guidance & my answer for Assignment 1#<Question 4>|Back to Question 4]]
## What is Big-Oh
> [!caution]
> This is a really scattered explanation of big-oh notation; it only tells you how to use big-oh, but I haven't explained why this method makes sense.
> 
> But this is enough to finish the assignment question.

In most cases, we only cares about the efficiency when the input is extremely large. (Since small inputs takes nearly no time)

The Big-Oh notation is a way to show the **approximate** growth rate of a math function when the input gets really big (to **infinity** $n\to \infty$). But what is the appropriate way to approximate becomes a problem. 

Here's the detail rules:

1. **Times a constant** number can be ignore

For example:
$$T(n)=10000n^2$$
The big oh is $O(n^2)$, ignore the $10000$

Even though the constant number is lower than 1, we need to ignore it. Like $T(n) = \frac{1}{2} n$, $O(n)=n$

2. **Add a constant** number can be ignore

For example:
$$T(n) = n + 10000$$
The big oh is $O(n)$, ignore the $10000$

3. Only leave the **"biggest" part**. Follows the following order:

$$O(1)<O(\log n)<O(n)<O(n\log n)<O(n^2)<O(n^3)<...<O(2^n)<O(3^n)<...<O(n!)$$

For example:
$$T(n) = n\log n + n+ n^2$$
Here, $n^2$ is the "biggest" part. The big oh is $O(n^2)$. Ignore other parts.


## Worst Case / Best Case / Average Case

When running code for a real problem, different cases may lead to significantly different running times.

For example, we have  $n$ different numbers in an array, and we want to find the number 7. If we search from the beginning until the end, here are four different cases:

**[Case 1]** The number 7 is the **first** element of the array. We only need to search for **1** item.

**[Case 2]** The number 7 is the **last** element of the array. We need to search all **n** items.

**[Case 3]** The number 7 is not included in the array. We still need to search all **n** items to find out.

**[Case 4]** The number 7 is the **x (1<x<n)** element of the array. We need to search **x** items.

In this example, we say:

- **Worst Case:** **Cases 2 and 3**. We need to search all **n** items, i.e. $O(n)$
- **Best Case:** **Case 1**. We only need to search **1** item, i.e. $O(1)$
- **Average Case:** **Case 4** when $x=\frac{1}{2} n$, i.e. the number 7 is in the exactly middle of the array. We only need to search $\frac{1}{2} n$ item, i.e. $O(n)$

An important thing to remember, in most cases, we'll analyse the running time regarding the **Worst Case**. Using the same principle that "only cares about the efficiency when the input is extremely large/time consumption is high"

[[Guidance & my answer for Assignment 1#<Question 5>|Back to Question 5]]
[[Guidance & my answer for Assignment 1#<Question 6>|Back to Question 6]]
## How to calculate Big-Oh

Instead of counting the exact number of operations, by knowing that we can ignore the constant in the equation, we only need to mainly focus on the loops related to the input.

For example

```cpp
for(int i = 0; i < n; i++) {
	if(i > 10) {
		cout << "Hi!" << end;
	} else {
		cout << "Good" << end;
		cout << "Bye!" << end;
	}
}
```
Even there's a if/else inside the loop and it's hard to count the exact number of operations. But because it only contains 1-layer for loop, so it's $O(n)$

For more complicated examples, always knows the principle:

> We only cares about the efficiency when the input is **extremely large**.  ($n\to \infty$)

So for the following code

```cpp
for (int i = 0; i < n; i++) {
	if (n > 200) {
		for (int j = 0; j < n; j++) {
			cout << "Hi!" << end;
		}
	} else {
		cout << "Bye!" << endl;
	}
}
```

When $n\to \infty$, only "if" part will runs. It is a 2-layers for loop, so it's $O(n^2)$

[[Guidance & my answer for Assignment 1#<Question 7>|Back to Question 7]]