# Programming Pearls

## Cracking the oyster
Further educate yourself about the problem than trying to solve it. 

### Requirement sort a disk file. 
 a. Why write a custom sort
 b. What are we sorting 
 c. How often the sort needs to be run
 d. If file is small and its integer , cant we sort in main memory 

**Context makes the problem clearer and also the performance requirement.**

#### Possible Options
  1. Disk based merge sort.  One Input -> Many work files -> One output file
  2. Bit map / vector representaion. Significantly reduce the runtime. 
  ```
  Initialize the array to zero
  insert 1 to the  present element index
  Print all the values
  ```
  3. Multi pass algorithm
      Read whole file once , sort only 0 - k ; next pass k , k + k .... 

## Aha! Algorithms

### Given sequential file , how to find a missing number
 Linear search if its less data , but if grows exponentially and becomes bottleneck ,  Binary Search log (n) in a sorted array. 
 If there is ample memory , we could try with bitmap technique too. 

### Rotate a one dimentional vector of size n  by i positions
     
### Given a dictionary of words , find all anagrams. 

