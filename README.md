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
A unique number that points to a single location on the heap.

* Pointer
*********
A location in memory that holds an address pointing to its corresponding value at that address.


Answer the following questions about memory management and dynamic variables
----------------------------------------------------------------------------

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
Using templates in collection classes allows for a broad range of data types that can be used within to store data within the object, rather than writing a separate class for every different type of data you need to store.  The template can also be used for more than just storing different types of data such as returning different types of data from functions.

* In normal C++ code the .h file contains the declarations, and the .cpp file contains implementations. Explain why this isn't the case with template-based collection classes.
*******************************************************************************************************************************************************************************
The implementations of a template-based collection class must be stored with its declarations. This is because a template is essentially a pattern that the complier will use to create a collection of classes.  In order for the compiler to understand what is going on, it must see both the template definition AND the declaration of the object.  Due to the fact that most compilers do not remember details of a previously looked at .cpp file, both the declaration and implementation must be stored in the same file.

20 - Using time and space analysis, justify the selection of a data structure for a given application
-----------------------------------------------------------------------------------------------------
Answer the following questions about choosing data structures. (5 points each)

* If I needed a data structure to store a set of strings, which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why. (Remember that a set doesn't have any order, and doesn't store duplicates. We can add items, remove items, and check to see if an item is already in the set.)
***********************************************************************************************************************************************************************************
A hash table seems to be the best data structure to use in this particular situation.  Collisions can be minimized with a carefully chosen hash function to determine where the strings are placed in the table, resulting in constant time for almost all add, remove, and find operations.  In the case of a collision during a call to add, we can check whether the value stored in the hash table at the position where the collision occured is actually the same or not.  If it is the same, we can return from add as to not store any duplicates.  If not, we can use modular arithmetic to place the value in the next-best position in the array, while at the same time making sure any other values with the same hash code are not actually the same value as the one we want to store.  There is no order in a hash table as the location in the table is determined only by the hash value.  Therefore, a hash table supports all the requirements for storing a set of strings.

* If I needed a data structure to store a grocery list, which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why.
***********************************************************************************************************************************************************************************
A linked list would be the best data structure to implement in this scenario.  Order is not detrimental in a grocery list, but if we wanted to put an item or multiple items in a specific location for any reason (such as grouping the items relative to where they are in the grocery store), we would be able to do so by placing the item(s) at a specific index.  Otherwise, we could simply pop the values onto the list for increased performance.  There is no way to avoid duplicate values in a linked list, but a duplicate on a grocery list is most certainly not harmful  - and could be proven rather useful in the right situation, such as a shopper wanting to purchase multiple of the same item.  

* If I needed a data structure to store student records so that I could look students up by Banner number, which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why.
***********************************************************************************************************************************************************************************
A hash table would be the best data structure to store student records.  The most expensive operation in a binary search tree is the remove function, and although I think it is safe to say that students are not being removed at a rate high enough to worry about it in that aspect.  However, removals still happen very often - and with possibly tens of thousands of students in the system, one remove could significantly decrease performance.  Although both data structures can quickly locate a value, the time both the find and add functions take in a binary search tree is proportional to the height of the tree.  Needless to say, the more students there are, the taller the tree.  In a hash table, in order to add, remove, and find a value, the Banner number is simply sent to the hash function which produces the location (or very close to it if there happens to be a collision) of the student's records.  Even if there is a collision, the number of records that we are sifting through is minimal, and therefore performance is almost completely unaffected given a large number of students.  

* Imagine that I'm implementing a network router. It needs to keep a queue of packets waiting to be sent out over the network, but this queue need a special ability: Different companies are going to pay me different amounts of money, and the packets from the highest paying company should be sent out first. That is, if company X paid 20 and company Y paid 10, then X's packets always get sent before Y's packets. Y only gets to send packets if X doesn't have any waiting. Which data structure (or data structures) that we learned this semester would be most appropriate? Carefully explain why.
***********************************************************************************************************************************************************************************
In this situation, a heap would be the best fit data structure.  When we add a packet to the heap, a priority number can be assigned to it corresponding to the company that is sending that packet.  In a heap, we can assign each element a priority number, which will determine what packet is popped off the heap when remove is called.  So if company X paid more money than any other company, their packets can be assigned the lowest priority number, causing them to always be sent out first. If we are worried about the order in which the packets are sent (i.e. - company X's 100 packets), it would not be difficult to implement an algorithm that searches for the lowest-priority packet that is furthest to the left and highest up the tree.  Doing so will retrieve the packets that were receieved and placed in the heap first, and therefore being the packets that should also be sent out first.  The data is not accessed in a network router after it is placed in storage until it is sent, so we don't need to worry about being able to access specific elements.  The retrieval of an element (which also removes the element) in a heap, as well as the addition of a new element both take time proportional to the height of the heap.