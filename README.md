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
    This problem arise in various guises. Some language provide rotation as primitive operation. Rotation means swapping adjacemtn blocks of unequal size (like a drag n drop in 
    document editor).
    abcdefgh ; n = 8 ; i = 3
    mouse and;  n = 9 ,  i = 6
    ouse mand
    
    #### Approach 1
    consider it as two segments in a vector and then do a swap 
    
    abc defgh
    if vector b is greater in size than a  , split to bl and br - left and right ; right is same in length as a 
    abc de fgh -> fgh de abc -> fgh de -> f de  -> edf -> de
    
    #### Approach 2
    View it as transforming an array from ab to ba. Involves a(reverse)*b ; a(reverse)*b(reverse) ; (a(reverse)*b(reverse))(reverse). 
    
    cba defgh (reverse A) reverse(0,i)
    cba hgfed (reverse B) reverse(i ,n)
    defghabc  (whole reverse) reverse (0 , n-1)
    
### Given a dictionary of words , find all anagrams. 
    Should be very efficient since the string length (factorial) words , say x should be compared against dictionary. 
    So total time is x *  x comparisons * time taken for 1 comparison
    #### Appproach 
    Words in anagram class has same signature.So bring together the words with same signature.
    
    This makes problem to 2 sub problem. 1. Create a signature. 2. Collect words with same signature. 
   
    ##### But what if you were given a word and dictionary and have to look-up anagrams?!
    If pre-processing is allowed , then   compute the signature and sort the dictionary words. Then do a binary search.
   
     Create empty hashmap H
     For each word in dictionary of length same as input:
      Create a key that is the word's letters sorted alphabetically (and forced to one case)
      Add the word to the list of words accessed by the hash key in H
  To check for all anagrams of a given word:
      Create a key that is the letters of the word, sorted (and forced to one case)
      Look up that key in H
      You now have a list of all anagrams
