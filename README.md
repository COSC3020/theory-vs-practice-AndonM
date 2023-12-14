[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11974266&assignment_repo_type=AssignmentRepo)
# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

1. In ignoring constant factors and lower order terms, an algorithm may run drastically slower than advertised. For example, consider an algorithm that runs in $O(n^2 + 1000000n)$ time. However, ignoring lower-order terms we simply get $O(n^2)$. One of these will, of course, run significantly slower than the other. However, standard runtime analysis practice will lead us to belive them as equal.

2. $\Omega$ and O are only loose bounds on how an algorithm may perform. Excluding $\Theta$, bounds can be particularly misleading. (either under or overestimating an algorithms performance)

3. In looking at a graph with different standard asymptotes, we see that everything from log(n) through n! appear to grow similarly with respect to the input size for small values of n. However, we see the true performance of an algortithm in play only when we look at large input sizes as that is when they will begin to diverge from one another. For an input size of 10 we will likely see roughly equal performance across the board for just about any algorithm. This can be misleading as their runtimes will quickly peel away from one another as the input size increases.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

Assuming a standard search time complexity of log(n), we can deduce that the search would take about 6.6 seconds. Taking the log of 1,000 we get 3. Expounding upon this, the log of 10,000 is 4, so log 10,000 is about 4/3 of log 1000. Taking this and multiplying with our original runtime (5 seconds) by 4/3 gets us our result.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

Apart from the explanations given in the first part, there are a few reasons why this could be the case specifically with a tree data structure. For starters, a big culprit could be that the tree is unbalanced. A BST performs no bettter than a linked list in the case that all of the nodes fall on one side. In the case that we have a purely unbalanced tree, we move from logarithmic time to search to linear time to search. Another possible factor in play is the cache. If node data is stored sparsely in memory this can wreck havoc on search times. Constantly swapping pages in and out of the cache will have a varying degree of impact on different hardware setups. However, such faulty serialization will never make things more speedy. Finally, in our first search, if the element we needed was at or near the top of the tree, finding it will not take long. However, if in the second search, the desired element ends up near the bottom, the performance can tank; especially if the other factors listed above are working against us in tandem with a deeply nested element.
