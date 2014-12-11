Portfolio - Document completion of the course's learning outcomes.
==================================================================


7 - Create an implementation of a Queue
---------------------------------------
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
The addition of a node in a binary search tree takes time proportional to the height of the newly added node.  However, the time it takes to add, as well as remove, a value in a hash table is usually linear (unless there is a collision, in which case the time adding a value takes is proportional to the number of values with the same hash-value).  There is one other exception to this, being when we must grow the backing array of the hash table.  The time it takes to remove a node from a BST is dependent on what type of node is being removed.  If the node being removed is a leaf or has one child, the time remove() takes is constant as we simply detach the node from its parent, or (in the case of having one child) have the parent of the node being removed adopt the child of the node being removed.  If the node being removed has two children, however, we must find a node (below the removed node) with less than 2 children that can legally replace the removed node.  Therefore, if we are removing a node with two children, the time remove() takes is proportional to the number of nodes underneath the node being removed.  Binary search trees are still useful because they allow us to quickly locate a value within them. The time it takes to add, remove, and find values in a hash table is critically dependent on the quality of its hash function.

* Adjacency List vs. Adjacency Matrix
**************************************
In an adjacency matrix, adding an edge, removing an edge, and finding an edge all work in constant time.  However, in an adjacency list, the only function that takes constant time is add.  Removing and finding an edge, as well as returning all outer edges in an adjacency list take time porportional to the number of edges that are stored in the list of the array that also contains the edge being removed or found.  Returning all the inner edges in an adjacency list is very slow; as it takes time proportional to the total number of values within all lists within the array.  In an adjacency matrix, returning the outer edges and returning the innder edges both take linear time.  The adjacency matrix is more useful when the number of edges is close to the square of the number of values in the matrix.

5 - Describe memory management in C++, and correctly use dynamic variables, including destructors
-------------------------------------------------------------------------------------------------
Define/describe each of the following terms, as they apply to memory management in C++

* The call stack (not to be confused with the stack data structure!)
********************************************************************
The call stack is a stack data structure mainly used to keep track of where to return to after a method is finished executing.  When a method is called, the address of the line that will be executed after the called method is pushed onto the call stack.  When the method is done, it pops the address off the top of the stack (since the stack is a LIFO data structure, the address at the top will always be the one to return to) and assigns its value to the instruction pointer, which 'points' to the next instruction to be executed.

* The heap (not to be confused with the heap data structure!)
*************************************************************
The heap is a heap data structure that has much more memory allocated towards it than the stack does.  The heap stores all of the variables and their data in a program, which can be then accessed and manipulated through pointers.  A single piece of data in the heap is referenced to by a pointer and represented by a single variable name in code.  The heap is slower than the stack simply because a pointer must be used to access memory on the heap.

* Address
*********
A unique number that defines where a certain piece of data is located in the heap.

* Pointer
*********
A location in memory that holds the address of a variable.


Answer the following questions about memory management and dynamic variables

* What is a memory leak, and why is it bad?
*******************************************
A memory leak is essentially an object stored in memory, of which the program using that object no longer has access to.  This mainly occurs when an object's address is deleted, but its data is not.  If a new object is created and assigned the address of an object that had only its address deleted, the pointer of the new object that was created now points to the data of the old object because the data was never deleted!  This can lead to bugs and even security breaches.

* What is a dangling pointer (or dangling reference), and why is it dangerous?
******************************************************************************
A dangling pointer is essentially a pointer that points to memory that is no longer valid.  The main cause of this is deleting the data associated with an object but not that object's pointer.  One very large problem associated with dangling pointers occurs when a malicious user alters the pointer (or the memory location the pointer is pointing to) so that the pointer now points to malicious code the hacker has written.

* What is a destructor, and why are they necessary (in C++) to prevent memory leaks? Why *aren't* they necessary in Java?
*************************************************************************************************************************
A destructor is used to destroy an object such that it leaves no memory leaks.  These are not necessary in Java due to the fact that Java has its own 'garbage collection system' that can detect when a variable should be thrown out - resulting in a slower, more secure program. 


5 - Create collection classes using templates in C++
----------------------------------------------------
Answer the following questions about templates in C++

* What is the main benefit of using templates when creating collection classes?
*******************************************************************************


* In normal C++ code the .h file contains the declarations, and the .cpp file contains implementations. Explain why this isn't the case with template-based collection classes.
*******************************************************************************************************************************************************************************


20 - Using time and space analysis, justify the selection of a data structure for a given application
-----------------------------------------------------------------------------------------------------
TODO: Answer the following questions about choosing data structures. (5 points each)

* If I needed a data structure to store a set of strings, which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why. (Remember that a set doesn't have any order, and doesn't store duplicates. We can add items, remove items, and check to see if an item is already in the set.)
* If I needed a data structure to store a grocery list, which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why.
* If I needed a data structure to store student records so that I could look students up by Banner number, which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why.
* Imagine that I'm implementing a network router. It needs to keep a queue of packets waiting to be sent out over the network, but this queue need a special ability: Different companies are going to pay me different amounts of money, and the packets from the highest paying company should be sent out first. That is, if company X paid 20 and company Y paid 10, then X's packets always get sent before Y's packets. Y only gets to send packets if X doesn't have any waiting. Which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why.
