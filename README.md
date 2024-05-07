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

1. Lower order terms that are disregarded during analysis can make a difference in actual performance between algorithms. When we are finding the runtime, we may have smaller terms such as in this example,
    $\ n^2 + 5n + 3$. In asymptotic analysis we drop the lower order terms and constants, meaning that the asymptotic complexity is $\ n^5 $.
2. Asymptotic analysis assumes that all constants take the same amount of time. In actual process, constants take different amounts of time, even though they may look the same on the screen. For example,  
   comparing integers takes less time than comparing strings. This also accounts for hardware differences. Although having different hardware would be a disregarded constant, we can't always know that all
   constants take the exact same amount of time for each machine. A machine may not have an FPU for floating point numbers, taking much more time when operating on them.
3. The input size also matters, especially with smaller inputs. With $O$, it bounds the running time for large enough inputs after a certain input n0. With inputs smaller than
   n0, it may not be as fast or efficient as other algorithms may be at a small size. In performance, a different algorithm may be better.
4. This also ties into the 3rd reason, but O is a loose bound. As long as it fulfills the definition, then it's a function in O. In theory, we can
   say that $\ f(n) \in O(n^2), f(n) \in O(n^3), f(n) \in O(2^n) $. Although this may be true, it tells us very little. It is more useful to get a tighter O bound, but it is technically correct.

If we find an element in a binary search tree with 1,000 element in 5 seconds, and the asymptotic complexity of searching a binary
search tree is $O(\log_2 n)$ , then that growth will still be logarithmic. 5 seconds / $log_2 (1000)$ = x / $log_2 (10000)$
So to get x, 5 * $log_2 (10000)$ / $log_2 (1000)$, which comes out to (66.435 / 9.96), or around 6.67 seconds. So it would take 6.67 seconds to 
find the same element in a 10,000 tree.

If it took 100 seconds it could be because...

1. Implementation can affect asymptotic analysis. The asymptotic analysis for a binary search tree is log n, but we don't know whether the implementation used is as efficient as log n. In the first time, it may
   be that the element was near the root of the tree. If we assume decent implementation and the best case scenario, it shouldn't have taken 5 seconds to find it. This implies that the implementation is extremely
   inefficient even for the best cases. In this case, an average case /worst case would take around 50 seconds. If we add 9,000 elements to that, the worst/average case takes much longer. The best case could be      6.667 for O(1), but the worst case where the height is around 13-14 depending on where it's at would account for a runtime of 100 seconds. In summary, tf the best case, or near best case scenario took 5       
   seconds due to bad implementation, then the worst, or even average case of 10,000 elements would take much longer which can create a runtime of 100 seconds.
  
2. Asymptotic complexity only considers the algorithm and not the machine you run it on. It's possible that the algorithm was run on different machines the first and second time and the hardware in those machines
   are different, or the value types were different. Asymptotic complexity also assumes that an action takes the same amount of time every time you do it. For the time complexity of a binary tree,
   we assume that each comparison takes the same amount of time every time. This may not be the case because of the difference in machine hardware. It's possible the first time the machine had an FPU, and the
   second time the machine didn't have an FPU. This would account for the time difference because even though ALUs can perform floating point subtraction, it takes much longer than an FPU does. This, also paired
   with the fact that it may have to make more comparisons due to a larger amount of input would account for the difference in time. This general reason can also be applied to value types. Floating point values
   will take more time to compare than integers, and strings will take longer to compare than characters. It could be that the first tree had only integers, but floating points were added, or even that the first
   tree had only characters, and then strings were added. This is especially the case if two long strings are compared because they compare character by character.
   
3. Another reason asymptotic complexity can be misleading that it doesn't account for anything other than the algorithm. This includes not having enough memory available becuase of other programs, switching
   the memory from virtual memory to the disk, or even having a better virtual machine. A tree with 1,000 elements is not going to need as much memory as a tree with 10,000 elements. Depending on the hardware
   the algorithm is run on, the program may not have sufficient memory to handle a tree with 10,000 elements, and may need to switch to the disk to store those elements as needed. Memory on the disk is much slower
   and could account for the unexpected increase in runtime. A machine only has a certain amount of RAM and virtual memory that this switch may be needed inorder to keep the values from being overwritten or
    corrupted. Another constraint on time complexity in terms of memory may be that there are other programs are utilizing the CPU or memory during runtime. This can lead to the program waiting to utilize the
   CPU. Different CPUs can run faster or slower, also further increasing or decreasing the runtime. In addition to this, the value of $\ n_0$ is also important in time complexity. It could be that for the
   first run, the input of 1,000 elements was below $\ n_0$, so it doesn't follow the asymptotic runtime meaning the runtime can tell us nothing valuable about it. For the second run, 10,000 elements could be past
   $\ n_0$, so the asymptotic complexity follows $\ O(log n)$.
   

   Sources used: TA, Discussed in Class ideas
