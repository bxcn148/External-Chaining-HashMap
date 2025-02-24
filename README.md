Download link :https://programming.engineering/product/external-chaining-hashmap/


# External-Chaining-HashMap
External Chaining HashMap
You are to code an ExternalChainingHashMap, a key-value hash map with an external chaining collision resolution strategy. A HashMap maps unique keys to values and allows O(1) average case lookup of a value when the key is known.

The table should not contain duplicate keys, but can contain duplicate values. In the event of try-ing to add a duplicate key, replace the value in the existing (key, value) pair with the new value and return the old value.

You should implement two constructors for this HashMap. As per the javadocs, you should use con-structor chaining to implement the no-arg constructor.

Capacity

The starting capacity of the ExternalChainingHashMap using the default constructor should be the constant INITIAL CAPACITY defined in ExternalChainingHashMap.java. Reference the constant as-is. Do not simply copy the value of the constant. Do not change the constant. Do not regrow the backing array when removing elements.

If adding to the table would cause the load factor (LF) to exceed (greater than, not greater than or equal to) the max load factor constant provided in the java file, the table should be resized to have a capacity of 2n + 1, where n is the current capacity before adding the parameterized element. See the javadocs for specific instructions on when to resize. There is a method called resize that you should use for resizing.

Hash and Compression Functions

You should not write your own hash functions for this assignment. Instead, use the hashCode() method that every Object has. For the compression function, mod by table length first, then take the absolute value (it must be done in this order to prevent overflow in certain cases). As a reminder, you should be using the hashCode() method on only the keys (and not the ExternalChainingMapEntry object itself) since that’s what is used to look up the values. After converting a key to an integer with a hash function, it must be compressed to fit in the array backing the HashMap.

External Chaining

Your hash map must implement an external chaining collision policy. That is, in the event of a collision, colliding entries are stored as a chain of ExternalChainingMapEntry objects at that index. As such, if you need to search for a key, you’ll need to traverse the entire chain at the hashed index to look for it. See ExternalChainingMapEntry.java to see what is stored and what methods are available for use; do not use Java’s LinkedList to handle the chaining functionality.

Adding

When adding a key/value pair to a hash map, add the pair to the front of the chain in the correct position. Also remember that keys are unique in a hash map, so you must ensure that duplicate keys are not added. Each index of the table should point to an ExternalChainingMapEntry that represents the head of a linked list. That linked list contains all elements that collide at that index.

Removing

When removing a key/value pair from a hash map using external chaining, you can safely remove the item unlike in open addressing techniques such as linear probing where you must use a DEL marker. Removing from a chain is very similar to removing from a Singly-Linked List, treating the first table

Homework 6: ExternalChainingHashMap Due: See Canvas

entry as the head, so refer to your notes and homework assignments from earlier in the course if you need a refresher. As usual, if the entry you are removing is the only entry at that index, you should make sure to null out that spot rather than leaving it there.

Homework 6: ExternalChainingHashMap Due: See Canvas

Grading

Here is the grading breakdown for the assignment. There are various deductions not listed that are incurred when breaking the rules listed in this PDF and in other various circumstances.

Methods:

constructor

2pts

put

18pts

remove

10pts

get

10pts

containsKey

10pts

keySet

5pts

values

5pts

resizeBackingTable

10pts

clear

5pts

Other:

Checkstyle

10pts

Efficiency

15pts

Total:

100pts

Provided

The following file(s) have been provided to you. There are several, but we’ve noted the ones to edit.

ExternalChainingHashMap.java

This is the class in which you will implement the ExternalChainingHashMap. Feel free to add private helper methods but do not add any new public methods, inner/nested classes, instance variables, or static variables.

ExternalChainingMapEntry.java

This class stores a key-value pair and the next reference for your hash map. Do not alter this file.

ExternalChainingHashMapStudentTest.java

This is the test class that contains a set of tests covering the basic operations on the ExternalChainingHashMap class. It is not intended to be exhaustive and does not guarantee any type of grade. Write your

own tests to ensure you cover all edge cases.

Deliverables

You must submit all of the following file(s) to the course Gradescope. Make sure all file(s) listed below are in each submission, as only the last submission will be graded. Make sure the filename(s) matches the filename(s) below, and thatonly the following file(s) are present. If you resubmit, be sure only one copy of each file is present in the submission. If there are multiple files, do not zip up the files before submitting; submit them all as separate files.

Once submitted, double check that it has uploaded properly on Gradescope. To do this, download your uploaded file(s) to a new folder, copy over the support file(s), recompile, and run. It is your sole responsibility to re-test your submission and discover editing oddities, upload issues, etc.

Homework 6: ExternalChainingHashMap Due: See Canvas

ExternalChainingHashMap.java
