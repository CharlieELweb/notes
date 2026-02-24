> [!danger] Remind
> > This is just my answer; it might contain mistakes. 
> 
> If you spot any mistakes or don't understand my answer, please tell me and correct them! It'll help a lot :)

You may first read through the [[Notes for Assignment 1]], then handling all the questions. Or, you can review the **related concepts** by clicking the **links**, and then address the question directly.

*(If the link does not go to the correct position, click the Table of Contents on the right to navigate to the correct part.)*
## Basic Concepts for Data Structure
- [[Notes for Assignment 1#What is an Algorithm?|What is an Algorithm?]]
- [[Notes for Assignment 1#What is Pseudocode?|What is Pseudocode?]]
- [[Notes for Assignment 1#What is a Pointer?|What is a Pointer?]]
- [[Notes for Assignment 1#Why use Pointer?|Why use Pointer?]]
- [[Notes for Assignment 1#What is Object/Class?|What is Object Class?]]
## <Question 1>

### Related Concepts
- [[Notes for Assignment 1#1. Linked List (Q1)|Linked List]]
### The Question

> **1a.** Suppose we have a pointer (prev) to a node in a singly linked list, and it is guaranteed not to be the last node in the list. Describe an algorithm to insert a new node (temp) immediately after this node in the list.
> 
> **1b.** In a singly linked list, write a member function `Search(ListNode* p, int k)` that searches for a node containing the value `k` in the linked list. If found, the function should return a pointer to the node; otherwise, it should return nullptr.

> [!hint]
> The process of adding a node & searching for a node in a linked list.
### My Answer
(Click to expand my answer)
> [!example]- My answer (1a-1b)
> **1a.** 
> To insert the new node `temp` after `prev`:
> 1. Set `temp -> next` to `prev -> next`
> 2. Set `prev->next` to `temp`.
> 
> **1b.**
> ```cpp
>ListNode* Search(ListNode* p, int k) {
>	while (p != nullptr) {
>		if (p -> val == k) { // found the value
>			return p;
>		}
>		p = p -> next; // move to the next node
>	}
>	return nullptr; // cannot find the node
>}
> ```

> [!note]- Explanation (1a-1b)
 > *(Don't include these in your answer, just for your understanding)*
 > 
> **[1a]** The process of [[Notes for Assignment 1#Add a node|Add a node]]
> **[1b]** The process of [[Notes for Assignment 1#Search a node|Search a node]], but begin from the node `p` till the end.

## <Question 2>
### Related Concepts
- [[Notes for Assignment 1#2. Stack (Q2)|Stack]]
### The Question
> **2a.** Given below is a pseudocode that uses a stack. What will be the output for input `CS2303DataStructures` for the given pseudocode:
> ```cpp
> declare a stack of characters;
> 
> while (there are more characters in the word to read)
> {
>	read a character;
>	push the character on the stack;
> }
> while (the stack is not empty)
> {
>	pop a character off the stack;
>	write the character to the screen;
> }
> ```
>
> **2b.** A single array `A[MAXSIZE]` is used to implement two stacks. The two stacks grow from opposite ends of the array. Variables `top1` and `top2` (`top1 < top2`) point to the location of the top most element in each of the stacks. If the space is to be used efficiently, what will be the condition for "stack full"?
>
> **2c.** Following is an incorrect pseudocode for the algorithm which is supposed to determine whether a sequence of parentheses is balanced or not. 
> For example, it should output “balanced” if the input is “ `((()))` ”, and output “unbalanced” if the input is “ `(()))` ”. 
> Please show why this pseudocode is incorrect by giving an example of an unbalanced sequence that the below code thinks is balanced, and rewrite the pseudocode to make it output the correct result.
> ```cpp
> declare a character stack;
>while (more input is available)
>{
>	read a character;
>	if (the character is a '(') {
>		push it on the stack;
>	}
>	else if (the character is a ')' and the stack is not empty) {
>		pop a character off the stack;
>	}
>	else {
>		print "unbalanced" and exit;
>	}
>}
> print "balanced";
> ```

> [!hint]
> Try running the pseudocode with simple examples to locate the issue.
### My Answer
(Click to expand my answer)
> [!example]- My answer (2a-2c)
> **2a.** 
`serutcurtSataD3032SC`
i.e. reverse of the original input
>
> **2b.** 
`top2 = top1 + 1`
>
> **2c.** 
> Example of unbalanced sequence: `()(`. 
> > *Or any example that adding several `(`  inside a balanced sequence, like `(()`, `()((`, `(()(())`*, etc. [You only need to write 1 of them in your answer]
> 
> Correct pseudocode:
> ```cpp
> declare a character stack;
>while (more input is available)
>{
>	read a character;
>	if (the character is a '(') {
>		push it on the stack;
>	}
>	else if (the character is a ')' and the stack is not empty) {
>		pop a character off the stack;
>	}
>	else {
>		print "unbalanced" and exit;
>	}
>}
>if (the stack is empty) {
>	print “balanced”;
>} else {
>	print “unbalanced”;
>}
> ```

> [!note]- Explanation (2a-2c)
 > *(Don't include these in your answer, just for your understanding)*
 > 
> **[2a]** [[Notes for Assignment 1#LIFO(Last In First Out) Principle|LIFO(Last In First Out) Principle]] 
> 
> **[2b]** One stack grows from the left, another grows from the right. So when the `top1` (left top) and `top2`(right) are neighbours, the stack is full.
> 
> **[2c]** 
> The original code only ensures that every ) has a matching ( before it, but doesn't verify that the number of ( and ) is the same.
> To fix the problem, we'll detect whether the stack is empty after the whole process. If it's empty, it shows that the number of `(` and `)` is the same. 
> 

## <Question 3>
### Related Concepts
- [[Notes for Assignment 1#3. Queue (Q3)|Queue]]
### The Question
> **3.** Write a C++ program or pseudocode to implement a queue using the stack data structure.
> The implementation should support enqueue and dequeue operations, utilising only the standard push and pop operations of a stack. (Tip: You can consider using two stacks.)

> [!hint]
> What is the difference between a **stack** and a **queue**?
### My Answer
(Click to expand my answer)
> [!example]- My answer (3)
> Pseudocode version:
> ```cpp
> class Queue {
> 	declare two integer stacks: stack1, stack2;
> 	
> 	void enqueue(int val) {
> 		while(stack1 is not empty) {
> 			push stack1's top to stack 2;
> 			pop the stack1's top;
> 		}
> 		push val to stack1;
> 		while(stack2 is not empty) {
> 			push stack2's top to stack 1;
> 			pop the stack2's top;
> 		}
> 	}
> 	
> 	int dequeue() {
> 		if(stack1 is empty) {
> 			return queue empty error code;
> 		}
> 		int rear = stack1's top;
> 		pop the stack1's top;
> 		return rear;
> 	}
> }
> ```
> 
> ***/OR/***
> 
> C++ version:
> ```cpp
> class Queue {
> 	stack<int> stack1, stack2;
> 	
> 	void enqueue(int val) {
> 		while (!stack1.empty()) {
> 			stack2.push(stack1.top());
> 			stack1.pop();
> 		}
> 		stack1.push(val);
> 		while (!stack2.empty()) {
> 			stack1.push(stack2.top());
> 			stack2.pop();
> 		}
> 	}
> 	int dequeue() {
> 		if (stack1.empty()) {
> 			return -1; // Queue empty
> 		}
> 		int rear = stack1.top();
> 		stack1.pop();
> 		return rear;
> 	}
> }
> ```
> 

> [!note]- Explanation (3)
 > *(Don't include these in your answer, just for your understanding)*
 > 
> We use `stack1` to store the queue, with its top as the front and its bottom as the rear.
> 
> In the `dequeue()` process, we simply pop the top value from `stack1`.
> 
> For the `enqueue()` process, to add a value to the bottom of `stack1`, we create a temporary stack, stack2, to store the `stack1` values. 
> After pushing the value to the bottom of `stack1`, we push all the values from stack2 back into stack1.

## <Question 4>
### Related Concepts
- [[Notes for Assignment 1#How to predict the running time| How to predict the running time]]

### The Question
> A program takes 0.5 seconds to process an input of size 30. Estimate the running time when the input size increases to 1000, assuming the running time follows each of the following functions.
> - **4a.** $T(n)=n$ (linear)
> - **4b.** $T(n)=100n^2$ (quadratic)
> - **4c.** $T(n)=2n^3$ (cubic)
> - **4d.** $T(n)=2^n$

> [!hint]
> Do some math! For **4a**-**4c**, you may use a calculator. But for **4d**, you need some basic exponent calculation.
### My Answer
(Click to expand my answer)
> [!example]- My answer (4a-4d)
> **[4a]**
> Number of operations T(n)=n, so the input size of 30 corresponds to 30 operations, which takes 0.5 seconds.
> 
> Thus, 1 operation takes 0.5/30 = 1/60 second.
> 
> When the input size increases to 1000, it corresponds to 1000 operations, which takes 1000 \* 1/60 = **16.67** seconds.
> 
> **[4b]**
> Number of operations T(n)=100n^2, so the input size of 30 corresponds to 100 \* 30^2 = 90,000 operations, which takes 0.5 seconds.
> 
> Thus, 1 operation takes 0.5/90,000 = 1/180,000 seconds.
> 
> When the input size increases to 1000, it corresponds to 100 \* 1000^2 = 100,000,000 operations, which takes 100,000,000 \* 1/180,000 = **555.56** seconds.
> 
> **[4c]**
> Number of operations T(n)=2n^3, so the input size of 30 corresponds to 2 \* 30^3 = 54,000 operations, which takes 0.5 seconds.
> 
> Thus, 1 operation takes 0.5/54,000 = 1/108,000 seconds.
> 
> When the input size increases to 1000, it corresponds to 2 \* 1000^3 = 2,000,000,000 operations, which takes 2,000,000,000 \* 1/108,000 = **18518.52** seconds.
> 
> **[4d]**
> Number of operations T(n)=2^n, so the input size of 30 corresponds to 2^30 operations, which takes 0.5 seconds.
> 
> Thus, 1 operation takes 0.5/2^30 = 1/2^31 seconds.
> 
> When the input size increases to 1000, it corresponds to 2^1000 operations, which takes 2^1000 \* 1/2^31 = **2^969** seconds.

## <Question 5>
### Related Concepts
- [[Notes for Assignment 1#What is Big-Oh|What is Big-Oh]]
- [[Notes for Assignment 1#Worst Case / Best Case / Average Case | Worst Case / Best Case / Average Case]]

### The Question
> Answer the following questions by analysing the program complexity.
> 
> **5a.** Suppose program 1 has worst case running time $T_1(n)=3n^2+100n\log n+9$, program 2 has worst case running time $T_2(n)=2^n+n$, and they can output the same results. Which program do you choose? Explain the reasons for your choice.
> 
> **5b.** Suppose program 1 has best case running time $T_1(n)=3n^2$, program 2 has best case running time $T_2(n)= n$, and they can output the same results. Which program do you choose? Explain the reasons for your answer.

> [!hint]
> What is the difference between **5a** and **5b**?


### My Answer
(Click to expand my answer)
> [!example]- My answer (5a-5b)
> **[5a]**
> **Program 1**
> 
> T1(n) = O(n^2), T2(n) = O(2^n).
> Since n\^2 grows much slower than 2\^n, the running time of program 1 will be much shorter than program 2.
> 
> **[5b]**
> **Can not decide**
> 
> The running times only matter when the input size gets really big. So we need to see the worst-case running time.
## <Question 6>
### Related Concepts
- [[Notes for Assignment 1#Worst Case / Best Case / Average Case | Worst Case / Best Case / Average Case]]

### The Question
> **6.** You are given a task to find whether the first word of a paragraph appears at least twice in the paragraph, and you decide to write a program to scan the word one by one from the very beginning of the text. What’s the worst case for your program? Describe the situation for the worst case and explain why.

> [!hint]
> The worst case may contain more than 1.
### My Answer
(Click to expand my answer)
> [!example]- My answer (6)
> The worst case happens when the first word only appears once, or the second appearance of the first is the last word of the paragraph.
> Because in these two cases, the program has to go through the entire paragraph from the beginning to the end.

## <Question 7>
### Related Concepts
- [[Notes for Assignment 1#How to calculate Big-Oh | How to calculate Big-Oh]]

### The Question

> Analyse the running time of the following programs and explain your answers.
> **7a.**
>```cpp
> void function1(int n)
> {
> 	int i,j;
> 	int x=200;
> 	for(i=0;i<n;i++)
> 	{
> 		if(x>100)
> 			x--;
> 		for(j=0;j<n;j++)
> 			x+=j;
> 	}
> }
> ```
> **7b.**
> ```cpp
> void function2 (int n)
> {
> 	int i,j;
> 	int x=100;
> 	for(i=0;i<n;i++)
> 	{
> 		if(x>200)
> 			for(j=0;j<n;j++)
> 				x-=j;
> 		else
> 			x++;
> 	}
> }
> ```

> [!hint]
>  7b is a kinda hard question, think carefully  approximately how many operations it will runs when `n` is very big, $n\to \infty$)

### My Answer
(Click to expand my answer)

> [!example]- My answer (7a-7b)
> **[7a]**
> **O(n^2)**
> There's a two-layer nested for loop from 0 to n.
> 
> **[7b]**
> **O(n)**
> When n is really big, after 100 iterations of the outer loop, x will be greater than 200, and the inner loop will be executed. However, after completing the inner loop, x will be extremely small and will never exceed 200 in the following iterations. So the inner loop will execute only once. Thus, the total number of operations for function2 is approximately 2n. So the running time is O(n).