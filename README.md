[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11974266&assignment_repo_type=AssignmentRepo)
# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

  1. In giving the final reduced answer for an algorithms time complexity, constant factors and lower-order terms tend to be left off with only the fastest growing term left front and center. In some cases, this
     is not a big deal; however, in others this can drastically hinder the actual expected performance.
 
  3. In working with actual production data, the ideology of asymptotic complexity tends to break down. In general, the data algorithms actually processes span across different types and often cover a huge
     range. In some cases, this may serve to either produce better than expected results. Unfortunately in others, much worse than what we're initially led to believe.

  4. In the real world, hardware and compiler optimizations can severely detract and/or add to a program's execution time. Running any program on the world's latest and greatest super computers will (of course)
     spit out greatly lower run times than any computer from the '80s. Furthermore, as compilers become more sophisticated they will further optimize our programs behind the scenes to hopefully enhance
     performance.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

  Assuming a standard search time complexity of log(n), we can deduce that the search would take ~6 seconds. Given how logarithmic operations scale with input size, we can safely assume the extra 9,000 elements
  would do little in the way of bumping up the search time.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

  Apart from the explanations given in the first part, there are a few reasons why this could be the case specifically with a tree data structure. For starters, a big culprit could be that the tree is
  unbalanced. A BST performs no bettter than a linked list in the case that all of the nodes fall on one side. Another rationale is the cache. If node data is stored sparsely in memory this can wreck
  havoc on search times. Finally, we can fall back to the simple explanation that in the first case, the element we were searching for fell near the top of the tree whereas with the larger tree, perhaps the
  element we needed was closer to the bottom of the tree meaning it will take more time to get to regardless of all the other factors at play.

  

Add your answers to this markdown file.
