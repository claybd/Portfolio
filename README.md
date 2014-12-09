Portfolio
=========
Document completion of the course's learning outcomes.

Instructions
====
The goal of this is to make it very easy for me (or an employer, or a teaching assistant) to see whether or not you have mastered the material of the class. The hope is that I would be able to grade your work without downloading and compiling your code. For labs, I can grade them by inspecting the code. For projects you must provide a video demonstrations of your programs. Some questions require essay responses.

Important
=========
If you prefer, you may turn this in to me via email, instead of hosting it on GitHub. Please talk to me about it during office hours or before or after class.

Body of portfolio
====

7 - Create an implementation of a Queue
----
https://github.com/claybd/03_Queue_Lab


7 - Create an implementation of a List
--------------------------------------
https://github.com/claybd/04_Linked_List_Lab


7 - Create an implementation of a Binary Search Tree
----------------------------------------------------
https://github.com/claybd/06_BST_Lab


7 - Create an implementation of a Hash Table
--------------------------------------------
https://github.com/claybd/05_Hashing_Lab


7 - Create an implementation of a Heap
--------------------------------------
https://github.com/claybd/07_Heap_Lab


7 - Create an implementation of either Adjacency Lists or Adjacency Matrices
----------------------------------------------------------------------------
https://github.com/claybd/08_Graph_Lab


7 - Implement graph algorithms
------------------------------
TODO: Provide a link to your completed Vise project (only if you used graph traversal), or add a graph traversal to 08_Graph_Lab and provide a link


21 (7 points each) - Determine space and time requirements of common data structure methods
-------------------------------------------------------------------------------------------

* Array-based list vs. Linked List
***********************************
In an array-based list, adding/removing a single element to/from the list is proportional to the number of elements that we must shift.  If the array must be grown, it will take time proportional to the number of elements in the list to do so.  Getting and setting values at a certain location in the list both take linear time.

In a linked list, adding, removing, and finding a single element at a specific index all take linear time if the index at which the element is to be added or removed is either equal to 0 or one less than the number of items in the list.  However, if the index is not one of the two previously stated values, the running time of these operations is one plus the lesser of the two following values: the index OR (number of items - index).


* Binary Search Tree vs. Hash Table
************************************


* Adjacency List vs. Adjacency Matrix
**************************************
TODO

5 - Describe memory management in C++, and correctly use dynamic variables, including destructors
----
TODO: Define/describe each of the following terms, as they apply to memory management in C++

* The call stack (not to be confused with the stack data structure!)
* The heap (not to be confused with the heap data structure!)
* Address
* Pointer

TODO: Answer the following questions about memory management and dynamic variables

* What is a memory leak, and why is it bad?
* What is a dangling pointer (or dangling reference), and why is it dangerous?
* What is a destructor, and why are they necessary (in C++) to prevent memory leaks? Why *aren't* they necessary in Java?


5 - Create collection classes using templates in C++
----
TODO: Answer the following questions about templates in C++


20 - Using time and space analysis, justify the selection of a data structure for a given application
----
TODO: Answer the following questions about choosing data structures. (5 points each)

* If I needed a data structure to store a set of strings, which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why. (Remember that a set doesn't have any order, and doesn't store duplicates. We can add items, remove items, and check to see if an item is already in the set.)
* If I needed a data structure to store a grocery list, which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why.
* If I needed a data structure to store student records so that I could look students up by Banner number, which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why.
* Imagine that I'm implementing a network router. It needs to keep a queue of packets waiting to be sent out over the network, but this queue need a special ability: Different companies are going to pay me different amounts of money, and the packets from the highest paying company should be sent out first. That is, if company X paid 20 and company Y paid 10, then X's packets always get sent before Y's packets. Y only gets to send packets if X doesn't have any waiting. Which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why.
