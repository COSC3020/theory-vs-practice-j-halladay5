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
1. When we added 9,000 elements the tree may not still be balanced (if it ever was). The height of the subtrees could be completely different. Because the time to search the binary tree is
   dependent on the height of the subtree it exists in, if its in a subtree that is very skewed and unbalanced (like a chain) it will take longer. My reasoning behind this is because instead of with a
   node with two children where the number of comparisons possible is cut in half annd it grows logarithmically, a chain only has one child, so the comparisons made only decreased by one. So it would be
   more linear. This would be a worst case scenario.
2. Asymptotic complexity only considers the algorithm and not the machine you run it on. If the first time you run it on a computer with multiple cores, a powerful processor and CPU, and tons of storage
   it will run much better than if you used a $150 computer from walmart that takes 20 seconds to open a tab the second time. If the computer doesn't have enough memory or the processor is slow it could
   take much longer. Asymptotic complexity doesn't account for inefficient hardware. The $150 laptop probably would've crashed anyway.
3. The structure of the tree has changed and we don't know what the values of the elements are. If the element we are searching for was near the root of the binary tree, and it rebalanced itself,
   it may have been pushed to a much farther down subtree. We also don't know what kind of elements were added to the tree. They could be strings, objects, or numbers. If the binary search tree was implemented
   so that objects are compared, or strings are compared, then it will be slower. 
