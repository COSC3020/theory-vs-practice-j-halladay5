[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/FgMJElkj)
# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

Add your answers to this markdown file.

1. Constant factors that are disregarded during analysis can make a difference in actual performance between algorithms.
2. The type of machine you are working with and the implementation can make a large difference. On different machines or languages, it may be faster or shorter.
3. The input size also matters, especially with smaller inputs. With $O$, it bounds the running time for large enough inputs after a certain input n0. With inputs smaller than
   n0, it may not be as fast or efficient as other algorithms may be at a small size. In performance, a different algorithm may be better.

If we find an element in a binary search tree with 1,000 element in 5 seconds, and the asymptotic complexity of searching a binary
search tree is $O(\log_2 n)$ , then that growth will still be logarithmic. 5 seconds / $log_2 (1000)$ = x / $log_2 (10000)$
So to get x, 5 * $log_2 (10000)$ / $log_2 (1000)$, which comes out to (66.435 / 9.96), or around 6.67 seconds. So it would take 6.67 seconds to 
find the same element in a 10,000 tree.

If it took 100 seconds it could be because...

1. Implementation can affect asymptotic analysis. If the tree is unbalanced and skewed and is not implemented to correct itself, then the asymptotic complexity changes. The asymptotic complexity for a binary tree is $\ O(log n)$ when it is balanced,
    but in the case of an unbalanced, binary search tree the asymptotic complexity changes to linear time, much slower than $\ O(log n)$. Making sure that my argument is correct I looked up the runtime for a skewed, binary tree.   https://www.geeksforgeeks.org/complexity-different-operations-binary-tree-binary-search-tree-avl-tree/
An additional implementation change is the language or ALU that the program was run with. If those elements are objects or strings, they will take longer to compare compared to integers. Some ALUs differ in operation times. Comparing 2 (8-bit) positive numbers
is different than comparing 2 (8-bit) negative numbers. With strings, if the lengths of the same then the computer goes character by character comparing to see if they are equivalent, or if one is of greater value than the other. With objects, if we
happen to be looking at a variable within certain objects, we will need to use a method to obtain the number first. Different languages implement in different ways as well. All of these add to the run time that we don't see or may disregard. 
  
3. Asymptotic complexity only considers the algorithm and not the machine you run it on. If the first time you run it on a computer with multiple cores, a powerful processor and CPU, and tons of storage
   it will run much better than if you used a $150 computer from walmart that takes 20 seconds to open a tab the second time. If the computer doesn't have enough memory or the processor is slow it could
   take much longer. Asymptotic complexity doesn't account for inefficient hardware. The $150 laptop probably would've crashed anyway.
   
4. With $\O$ we omit the constant factors when determining the asymptotic complexity. Although we estimate the run time to be 6.67 seconds, the constant factor is not included in that. The constant factor that was omitted could affect
   our actual run time. If the constant factor was somewhere around 15, then the time it would take would be around 100 seconds. 

   Sources used: TA
